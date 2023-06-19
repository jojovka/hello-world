# hello-world
Just my first repository


@Service("r360_EmailReportsService")
public class EmailReportsService {
    public static final String SUCCESS_CODE = "Successful";
    @Autowired
    private EmailTemplates emailTemplates;
    @Autowired
    private Emailer emailer;

    public String emailFisRsReport(String templateCode, String date, String recipients) {
        try {
            EmailTemplate newTemplate = emailTemplates.buildFromTemplate(templateCode)
                    .setTo(recipients)
                    .build();
            SimpleDateFormat format = new SimpleDateFormat("yyyy-MM-dd");
            Date date2 = format.parse(date);
            Map<String, Object> paramsMap = new HashMap<>();
            paramsMap.put("rep_date", date2);
            EmailInfo emailInfo = emailTemplates.generateEmail(newTemplate, paramsMap);
            emailer.sendEmail(emailInfo);
            return SUCCESS_CODE;
        } catch (TemplateNotFoundException | EmailException | ReportParameterTypeChangedException | ParseException e) {
            throw new RuntimeException(e);
        }
    }
}

java.lang.RuntimeException: Yerbol.Shayakhmetov@eubank.kz; zarina.zhaparova@eubank.kz : Failed messages: com.sun.mail.smtp.SMTPSendFailedException: 552 #5.3.4 message size exceeds limit
