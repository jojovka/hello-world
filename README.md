# hello-world
Just my first repository

package kz.eub.report360.app;

import io.jmix.email.EmailException;
import io.jmix.email.EmailInfo;
import io.jmix.email.Emailer;
import io.jmix.emailtemplates.EmailTemplates;
import io.jmix.emailtemplates.entity.EmailTemplate;
import io.jmix.emailtemplates.exception.ReportParameterTypeChangedException;
import io.jmix.emailtemplates.exception.TemplateNotFoundException;
import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.stereotype.Service;

import java.util.Map;

@Service("r360_EmailService")
public class EmailService {
    public static final String SUCCESS_CODE = "Successfully";
    @Autowired
    private EmailTemplates emailTemplates;
    @Autowired
    private Emailer emailer;

    public String emailReport(String templateCode, String recipients, Map<String, Object> params) {
        try {
            EmailTemplate newTemplate = emailTemplates.buildFromTemplate(templateCode)
                    .setTo(recipients)
                    .build();
            EmailInfo emailInfo = emailTemplates.generateEmail(newTemplate, params);
            emailer.sendEmail(emailInfo);
            return SUCCESS_CODE;
        } catch (TemplateNotFoundException | EmailException | ReportParameterTypeChangedException e) {
            throw new RuntimeException(e);
        }
    }
}
