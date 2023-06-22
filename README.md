# hello-world
Just my first repository


<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.1//EN" "http://www.w3.org/TR/xhtml11/DTD/xhtml11.dtd">
<html xmlns="http://www.w3.org/1999/xhtml">
<head>
    <meta charset="UTF-8" />
</head>
<body>
<#assign head = Root.bands.head/> 
<#assign body = Root.bands.body /> 
<#assign body2 = Root.bands.body2 /> 
<#assign body3 = Root.bands.body3 /> 
<#assign body4 = Root.bands.body4 />
<#assign body5 = Root.bands.body5 />
<#assign body6 = Root.bands.body6 />
<#assign body7 = Root.bands.body7 />
<#assign body8 = Root.bands.body8 />
<#assign body9 = Root.bands.body9 />
<#assign body10 = Root.bands.body10 />
<#assign body11 = Root.bands.body11 />
<#assign body12 = Root.bands.body12 />
<#assign body13 = Root.bands.body13 />
<#assign body14 = Root.bands.body14 />
<#assign body15 = Root.bands.body15 />
<h3 style="font-family: verdana;">
<#list head as head>
СВЕРОЧНЫЙ ОТЧЕТ ПО ВЫДАННЫМ ЗАЙМАМ МЕЖДУ СИСТЕМАМИ FIS И RS-LOANS ЗА ${head.fields.rep_date}</h3>
</#list>
<#list body as body>
<#list body2 as body2>
<p style="font-size:13px; font-family: verdana;"> 
Количество профинансированных заявок в FIS: <b>${body.fields.count}</b> , количество договоров в RS-Loans: <b>${body2.fields.count} </b></p>
</#list>
</#list> 
<p style="font-size:13px; font-family: verdana;"> 
Есть в FIS, отсутствуют в RS-Loans: 
</p>
<table border="1">
<tr style="background-color: #c2c3b5; font-size:13px; font-family: verdana;">
<td style="padding: 0 5 0 5;">№</td>
<td style="padding: 0 5 0 5;">Дата заведения заявки/дата договора</td>
<td style="padding: 0 5 0 5;">№ договора / № заявки</td>
<td style="padding: 0 5 0 5;">Сумма финансирования</td>
<td style="padding: 0 5 0 5;">ФИО клиента</td>
<td style="padding: 0 5 0 5;">ИИН клиента</td>
</tr>
 <#list body3 as body3>
<tr style="font-size:13px; font-family: verdana;">
<td  style="padding: 0 5 0 5;">${body3.fields.NUMM}</td>
<td  style="padding: 0 5 0 5;">${body3.fields.DVZ}</td>
<td  style="padding: 0 5 0 5;">${body3.fields.NOM}</td>
<td  style="padding: 0 5 0 5;">${body3.fields.SUMM}</td>
<td  style="padding: 0 5 0 5;">${body3.fields.FIO}</td>
<td  style="padding: 0 5 0 5;">${body3.fields.IIN}</td>
</tr>
</#list>
</table>
<p style="font-size:13px; font-family: verdana;"> 
Есть в RS-Loans, отсутствуют в FIS: 
</p>
<table border="1">
<tr style="background-color: #c2c3b5; font-size:13px; font-family: verdana;">
<td style="padding: 0 5 0 5; font-size:13px; font-family: verdana;">№</td>
<td style="padding: 0 5 0 5; font-size:13px; font-family: verdana;">Дата заведения заявки/дата договора</td>
<td style="padding: 0 5 0 5; font-size:13px; font-family: verdana;">№ договора / № заявки</td>
<td style="padding: 0 5 0 5; font-size:13px; font-family: verdana;">Сумма финансирования</td>
<td style="padding: 0 5 0 5; font-size:13px; font-family: verdana;">ФИО клиента</td>
<td style="padding: 0 5 0 5; font-size:13px; font-family: verdana;">ИИН клиента</td>
</tr>
<#list body4 as body4>
<tr style="font-size:13px; font-family: verdana;">
<td style="padding: 0 5 0 5;">${body4.fields.NUMM}</td>
<td style="padding: 0 5 0 5;">${body4.fields.REGDATE}</td>
<td style="padding: 0 5 0 5;">${body4.fields.DOGNUM}</td>
<td style="padding: 0 5 0 5;">${body4.fields.SUMM}</td>
<td style="padding: 0 5 0 5;">${body4.fields.FIO}</td>
<td style="padding: 0 5 0 5;">${body4.fields.IIN}</td>
</tr>
</#list>
</table>
<p style="font-size:13px; font-family: verdana;"> 1. Расхождение в поле ИИН: </p>
<table border="1">
<tr style="background-color: #c2c3b5; font-size:13px; font-family: verdana;">
<td style="padding: 0 5 0 5; font-size:13px; font-family: verdana;">№</td>
<td style="padding: 0 5 0 5; font-size:13px; font-family: verdana;">Дата заведения заявки/дата договора</td>
<td style="padding: 0 5 0 5; font-size:13px; font-family: verdana;">№ договора / № заявки</td>
<td style="padding: 0 5 0 5; font-size:13px; font-family: verdana;">Сумма финансирования</td>
<td style="padding: 0 5 0 5; font-size:13px; font-family: verdana;">ФИО клиента</td>
<td style="padding: 0 5 0 5; font-size:13px; font-family: verdana;">ИИН клиента</td>
<td style="padding: 0 5 0 5; font-size:13px; font-family: verdana;">Значение в ФИС</td>
<td style="padding: 0 5 0 5; font-size:13px; font-family: verdana;">Значение в РС</td>
</tr>
<#list body5 as body5>
<tr style="font-size:13px; font-family: verdana;">
<td style="padding: 0 5 0 5;">${body5.fields.NUMM}</td>
<td style="padding: 0 5 0 5;">${body5.fields.FINDATE}</td>
<td style="padding: 0 5 0 5;">${body5.fields.DOGNUM}</td>
<td style="padding: 0 5 0 5;">${body5.fields.FINSUM}</td>
<td style="padding: 0 5 0 5;">${body5.fields.FIO}</td>
<td style="padding: 0 5 0 5;">${body5.fields.IIN}</td>
<td style="padding: 0 5 0 5;">${body5.fields.TFIS}</td>
<td style="padding: 0 5 0 5;">${body5.fields.TRS}</td>
</tr>
</#list>
</table>
<p style="font-size:13px; font-family: verdana;"> 2. Расхождение в поле ФИО: </p>
<table border="1">
<tr style="background-color: #c2c3b5; font-size:13px; font-family: verdana;">
<td style="padding: 0 5 0 5; font-size:13px; font-family: verdana;">№</td>
<td style="padding: 0 5 0 5; font-size:13px; font-family: verdana;">Дата заведения заявки/дата договора</td>
<td style="padding: 0 5 0 5; font-size:13px; font-family: verdana;">№ договора / № заявки</td>
<td style="padding: 0 5 0 5; font-size:13px; font-family: verdana;">Сумма финансирования</td>
<td style="padding: 0 5 0 5; font-size:13px; font-family: verdana;">ФИО клиента</td>
<td style="padding: 0 5 0 5; font-size:13px; font-family: verdana;">ИИН клиента</td>
<td style="padding: 0 5 0 5; font-size:13px; font-family: verdana;">Значение в ФИС</td>
<td style="padding: 0 5 0 5; font-size:13px; font-family: verdana;">Значение в РС</td>
</tr>
<#list body6 as body6>
<tr style="font-size:13px; font-family: verdana;">
<td style="padding: 0 5 0 5;">${body6.fields.NUMM}</td>
<td style="padding: 0 5 0 5;">${body6.fields.FINDATE}</td>
<td style="padding: 0 5 0 5;">${body6.fields.DOGNUM}</td>
<td style="padding: 0 5 0 5;">${body6.fields.FINSUM}</td>
<td style="padding: 0 5 0 5;">${body6.fields.FIO}</td>
<td style="padding: 0 5 0 5;">${body6.fields.IIN}</td>
<td style="padding: 0 5 0 5;">${body6.fields.TFIS}</td>
<td style="padding: 0 5 0 5;">${body6.fields.TRS}</td>
</tr>
</#list>
</table>
<p style="font-size:13px; font-family: verdana;"> 3. Расхождение в поле Код клиента: </p>
<table border="1">
<tr style="background-color: #c2c3b5; font-size:13px; font-family: verdana;">
<td style="padding: 0 5 0 5; font-size:13px; font-family: verdana;">№</td>
<td style="padding: 0 5 0 5; font-size:13px; font-family: verdana;">Дата заведения заявки/дата договора</td>
<td style="padding: 0 5 0 5; font-size:13px; font-family: verdana;">№ договора / № заявки</td>
<td style="padding: 0 5 0 5; font-size:13px; font-family: verdana;">Сумма финансирования</td>
<td style="padding: 0 5 0 5; font-size:13px; font-family: verdana;">ФИО клиента</td>
<td style="padding: 0 5 0 5; font-size:13px; font-family: verdana;">ИИН клиента</td>
<td style="padding: 0 5 0 5; font-size:13px; font-family: verdana;">Значение в ФИС</td>
<td style="padding: 0 5 0 5; font-size:13px; font-family: verdana;">Значение в РС</td>
</tr>
<#list body7 as body7>
<tr style="font-size:13px; font-family: verdana;">
<td style="padding: 0 5 0 5;">${body7.fields.NUMM}</td>
<td style="padding: 0 5 0 5;">${body7.fields.FINDATE}</td>
<td style="padding: 0 5 0 5;">${body7.fields.DOGNUM}</td>
<td style="padding: 0 5 0 5;">${body7.fields.FINSUM}</td>
<td style="padding: 0 5 0 5;">${body7.fields.FIO}</td>
<td style="padding: 0 5 0 5;">${body7.fields.IIN}</td>
<td style="padding: 0 5 0 5;">${body7.fields.TFIS}</td>
<td style="padding: 0 5 0 5;">${body7.fields.TRS}</td>
</tr>
</#list>
</table>
<p style="font-size:13px; font-family: verdana;"> 4. Расхождение в поле Наименование торговой точки: </p>
<table border="1">
<tr style="background-color: #c2c3b5; font-size:13px; font-family: verdana;">
<td style="padding: 0 5 0 5; font-size:13px; font-family: verdana;">№</td>
<td style="padding: 0 5 0 5; font-size:13px; font-family: verdana;">Дата заведения заявки/дата договора</td>
<td style="padding: 0 5 0 5; font-size:13px; font-family: verdana;">№ договора / № заявки</td>
<td style="padding: 0 5 0 5; font-size:13px; font-family: verdana;">Сумма финансирования</td>
<td style="padding: 0 5 0 5; font-size:13px; font-family: verdana;">ФИО клиента</td>
<td style="padding: 0 5 0 5; font-size:13px; font-family: verdana;">ИИН клиента</td>
<td style="padding: 0 5 0 5; font-size:13px; font-family: verdana;">Значение в ФИС</td>
<td style="padding: 0 5 0 5; font-size:13px; font-family: verdana;">Значение в РС</td>
</tr>
<#list body8 as body8>
<tr style="font-size:13px; font-family: verdana;">
<td style="padding: 0 5 0 5;">${body8.fields.NUMM}</td>
<td style="padding: 0 5 0 5;">${body8.fields.FINDATE}</td>
<td style="padding: 0 5 0 5;">${body8.fields.DOGNUM}</td>
<td style="padding: 0 5 0 5;">${body8.fields.FINSUM}</td>
<td style="padding: 0 5 0 5;">${body8.fields.FIO}</td>
<td style="padding: 0 5 0 5;">${body8.fields.IIN}</td>
<td style="padding: 0 5 0 5;">${body8.fields.TFIS}</td>
<td style="padding: 0 5 0 5;">${body8.fields.TRS}</td>
</tr>
</#list>
</table>
<p style="font-size:13px; font-family: verdana;"> 5. Расхождение в поле Дата финансирования: </p>
<table border="1"><tr style="background-color: #c2c3b5; font-size:13px; font-family: verdana;">
<td style="padding: 0 5 0 5; font-size:13px; font-family: verdana;">№</td>
<td style="padding: 0 5 0 5; font-size:13px; font-family: verdana;">Дата заведения заявки/дата договора</td>
<td style="padding: 0 5 0 5; font-size:13px; font-family: verdana;">№ договора / № заявки</td>
<td style="padding: 0 5 0 5; font-size:13px; font-family: verdana;">Сумма финансирования</td>
<td style="padding: 0 5 0 5; font-size:13px; font-family: verdana;">ФИО клиента</td>
<td style="padding: 0 5 0 5; font-size:13px; font-family: verdana;">ИИН клиента</td>
<td style="padding: 0 5 0 5; font-size:13px; font-family: verdana;">Значение в ФИС</td>
<td style="padding: 0 5 0 5; font-size:13px; font-family: verdana;">Значение в РС</td>
</tr>
<#list body9 as body9>
<tr style="font-size:13px; font-family: verdana;">
<td style="padding: 0 5 0 5;">${body9.fields.NUMM}</td>
<td style="padding: 0 5 0 5;">${body9.fields.FINDATE}</td>
<td style="padding: 0 5 0 5;">${body9.fields.DOGNUM}</td>
<td style="padding: 0 5 0 5;">${body9.fields.FINSUM}</td>
<td style="padding: 0 5 0 5;">${body9.fields.FIO}</td>
<td style="padding: 0 5 0 5;">${body9.fields.IIN}</td>
<td style="padding: 0 5 0 5;">${body9.fields.TFIS}</td>
<td style="padding: 0 5 0 5;">${body9.fields.TRS}</td>
</tr>
</#list>
</table>
<p style="font-size:13px; font-family: verdana;"> 6. Расхождение в поле Дата окончания договора: </p>
<table border="1">
<tr style="background-color: #c2c3b5; font-size:13px; font-family: verdana;">
<td style="padding: 0 5 0 5; font-size:13px; font-family: verdana;">№</td>
<td style="padding: 0 5 0 5; font-size:13px; font-family: verdana;">Дата заведения заявки/дата договора</td>
<td style="padding: 0 5 0 5; font-size:13px; font-family: verdana;">№ договора / № заявки</td>
<td style="padding: 0 5 0 5; font-size:13px; font-family: verdana;">Сумма финансирования</td>
<td style="padding: 0 5 0 5; font-size:13px; font-family: verdana;">ФИО клиента</td>
<td style="padding: 0 5 0 5; font-size:13px; font-family: verdana;">ИИН клиента</td>
<td style="padding: 0 5 0 5; font-size:13px; font-family: verdana;">Значение в ФИС</td>
<td style="padding: 0 5 0 5; font-size:13px; font-family: verdana;">Значение в РС</td>
</tr>
<#list body10 as body10>
<tr style="font-size:13px; font-family: verdana;">
<td style="padding: 0 5 0 5;">${body10.fields.NUMM}</td>
<td style="padding: 0 5 0 5;">${body10.fields.FINDATE}</td>
<td style="padding: 0 5 0 5;">${body10.fields.DOGNUM}</td>
<td style="padding: 0 5 0 5;">${body10.fields.FINSUM}</td>
<td style="padding: 0 5 0 5;">${body10.fields.FIO}</td>
<td style="padding: 0 5 0 5;">${body10.fields.IIN}</td>
<td style="padding: 0 5 0 5;">${body10.fields.TFIS}</td>
<td style="padding: 0 5 0 5;">${body10.fields.TRS}</td>
</tr>
</#list>
</table>
<p style="font-size:13px; font-family: verdana;"> 7. Расхождение в поле Сумма финансирования: </p>
<table border="1">
<tr style="background-color: #c2c3b5; font-size:13px; font-family: verdana;">
<td style="padding: 0 5 0 5; font-size:13px; font-family: verdana;">№</td>
<td style="padding: 0 5 0 5; font-size:13px; font-family: verdana;">Дата заведения заявки/дата договора</td>
<td style="padding: 0 5 0 5; font-size:13px; font-family: verdana;">№ договора / № заявки</td>
<td style="padding: 0 5 0 5; font-size:13px; font-family: verdana;">Сумма финансирования</td>
<td style="padding: 0 5 0 5; font-size:13px; font-family: verdana;">ФИО клиента</td>
<td style="padding: 0 5 0 5; font-size:13px; font-family: verdana;">ИИН клиента</td>
<td style="padding: 0 5 0 5; font-size:13px; font-family: verdana;">Значение в ФИС</td>
<td style="padding: 0 5 0 5; font-size:13px; font-family: verdana;">Значение в РС</td>
</tr>
<#list body11 as body11>
<tr style="font-size:13px; font-family: verdana;">
<td style="padding: 0 5 0 5;">${body11.fields.NUMM}</td>
<td style="padding: 0 5 0 5;">${body11.fields.FINDATE}</td>
<td style="padding: 0 5 0 5;">${body11.fields.DOGNUM}</td>
<td style="padding: 0 5 0 5;">${body11.fields.FINSUM}</td>
<td style="padding: 0 5 0 5;">${body11.fields.FIO}</td>
<td style="padding: 0 5 0 5;">${body11.fields.IIN}</td>
<td style="padding: 0 5 0 5;">${body11.fields.TFIS}</td>
<td style="padding: 0 5 0 5;">${body11.fields.TRS}</td>
</tr>
</#list>
</table>
<p style="font-size:13px; font-family: verdana;"> 8. Расхождение в поле Дата первого платежа: </p>
<table border="1"><tr style="background-color: #c2c3b5; font-size:13px; font-family: verdana;">
<td style="padding: 0 5 0 5; font-size:13px; font-family: verdana;">№</td>
<td style="padding: 0 5 0 5; font-size:13px; font-family: verdana;">Дата заведения заявки/дата договора</td>
<td style="padding: 0 5 0 5; font-size:13px; font-family: verdana;">№ договора / № заявки</td>
<td style="padding: 0 5 0 5; font-size:13px; font-family: verdana;">Сумма финансирования</td>
<td style="padding: 0 5 0 5; font-size:13px; font-family: verdana;">ФИО клиента</td>
<td style="padding: 0 5 0 5; font-size:13px; font-family: verdana;">ИИН клиента</td>
<td style="padding: 0 5 0 5; font-size:13px; font-family: verdana;">Значение в ФИС</td>
<td style="padding: 0 5 0 5; font-size:13px; font-family: verdana;">Значение в РС</td>
</tr>
<#list body12 as body12>
<tr style="font-size:13px; font-family: verdana;">
<td style="padding: 0 5 0 5;">${body12.fields.NUMM}</td>
<td style="padding: 0 5 0 5;">${body12.fields.FINDATE}</td>
<td style="padding: 0 5 0 5;">${body12.fields.DOGNUM}</td>
<td style="padding: 0 5 0 5;">${body12.fields.FINSUM}</td>
<td style="padding: 0 5 0 5;">${body12.fields.FIO}</td>
<td style="padding: 0 5 0 5;">${body12.fields.IIN}</td>
<td style="padding: 0 5 0 5;">${body12.fields.TFIS}</td>
<td style="padding: 0 5 0 5;">${body12.fields.TRS}</td>
</tr>
</#list>
</table>
<p style="font-size:13px; font-family: verdana;"> 9. Расхождение в поле Перечисление в страховую компанию (сумма страховой премии): </p>
<table border="1">
<tr style="background-color: #c2c3b5; font-size:13px; font-family: verdana;">
<td style="padding: 0 5 0 5; font-size:13px; font-family: verdana;">№</td>
<td style="padding: 0 5 0 5; font-size:13px; font-family: verdana;">Дата заведения заявки/дата договора</td>
<td style="padding: 0 5 0 5; font-size:13px; font-family: verdana;">№ договора / № заявки</td>
<td style="padding: 0 5 0 5; font-size:13px; font-family: verdana;">Сумма финансирования</td>
<td style="padding: 0 5 0 5; font-size:13px; font-family: verdana;">ФИО клиента</td>
<td style="padding: 0 5 0 5; font-size:13px; font-family: verdana;">ИИН клиента</td>
<td style="padding: 0 5 0 5; font-size:13px; font-family: verdana;">Значение в ФИС</td>
<td style="padding: 0 5 0 5; font-size:13px; font-family: verdana;">Значение в РС</td>
</tr>
<#list body13 as body13>
<tr style="font-size:13px; font-family: verdana;">
<td style="padding: 0 5 0 5;">${body13.fields.NUMM}</td>
<td style="padding: 0 5 0 5;">${body13.fields.FINDATE}</td>
<td style="padding: 0 5 0 5;">${body13.fields.DOGNUM}</td>
<td style="padding: 0 5 0 5;">${body13.fields.FINSUM}</td>
<td style="padding: 0 5 0 5;">${body13.fields.FIO}</td>
<td style="padding: 0 5 0 5;">${body13.fields.IIN}</td>
<td style="padding: 0 5 0 5;">${body13.fields.TFIS}</td>
<td style="padding: 0 5 0 5;">${body13.fields.TRS}</td>
</tr>
</#list>
</table>
<p style="font-size:13px; font-family: verdana;"> 10. Расхождение в поле Срок займа (в месяцах): </p>
<table border="1">
<tr style="background-color: #c2c3b5; font-size:13px; font-family: verdana;">
<td style="padding: 0 5 0 5; font-size:13px; font-family: verdana;">№</td>
<td style="padding: 0 5 0 5; font-size:13px; font-family: verdana;">Дата заведения заявки/дата договора</td>
<td style="padding: 0 5 0 5; font-size:13px; font-family: verdana;">№ договора / № заявки</td>
<td style="padding: 0 5 0 5; font-size:13px; font-family: verdana;">Сумма финансирования</td>
<td style="padding: 0 5 0 5; font-size:13px; font-family: verdana;">ФИО клиента</td>
<td style="padding: 0 5 0 5; font-size:13px; font-family: verdana;">ИИН клиента</td>
<td style="padding: 0 5 0 5; font-size:13px; font-family: verdana;">Значение в ФИС</td>
<td style="padding: 0 5 0 5; font-size:13px; font-family: verdana;">Значение в РС</td>
</tr>
<#list body14 as body14>
<tr style="font-size:13px; font-family: verdana;">
<td style="padding: 0 5 0 5;">${body14.fields.NUMM}</td>
<td style="padding: 0 5 0 5;">${body14.fields.FINDATE}</td>
<td style="padding: 0 5 0 5;">${body14.fields.DOGNUM}</td>
<td style="padding: 0 5 0 5;">${body14.fields.FINSUM}</td>
<td style="padding: 0 5 0 5;">${body14.fields.FIO}</td>
<td style="padding: 0 5 0 5;">${body14.fields.IIN}</td>
<td style="padding: 0 5 0 5;">${body14.fields.TFIS}</td>
<td style="padding: 0 5 0 5;">${body14.fields.TRS}</td>
</tr>
</#list>
</table>
<p style="font-size:13px; font-family: verdana;"> 11. Расхождение в поле Тариф: </p>
<table border="1"><tr style="background-color: #c2c3b5; font-size:13px; font-family: verdana;">
<td style="padding: 0 5 0 5; font-size:13px; font-family: verdana;">№</td>
<td style="padding: 0 5 0 5; font-size:13px; font-family: verdana;">Дата заведения заявки/дата договора</td>
<td style="padding: 0 5 0 5; font-size:13px; font-family: verdana;">№ договора / № заявки</td>
<td style="padding: 0 5 0 5; font-size:13px; font-family: verdana;">Сумма финансирования</td>
<td style="padding: 0 5 0 5; font-size:13px; font-family: verdana;">ФИО клиента</td>
<td style="padding: 0 5 0 5; font-size:13px; font-family: verdana;">ИИН клиента</td>
<td style="padding: 0 5 0 5; font-size:13px; font-family: verdana;">Значение в ФИС</td>
<td style="padding: 0 5 0 5; font-size:13px; font-family: verdana;">Значение в РС</td>
</tr>
<#list body15 as body15>
<tr style="font-size:13px; font-family: verdana;">
<td style="padding: 0 5 0 5;">${body15.fields.NUMM}</td>
<td style="padding: 0 5 0 5;">${body15.fields.FINDATE}</td>
<td style="padding: 0 5 0 5;">${body15.fields.DOGNUM}</td>
<td style="padding: 0 5 0 5;">${body15.fields.FINSUM}</td>
<td style="padding: 0 5 0 5;">${body15.fields.FIO}</td>
<td style="padding: 0 5 0 5;">${body15.fields.IIN}</td>
<td style="padding: 0 5 0 5;">${body15.fields.TFIS}</td>
<td style="padding: 0 5 0 5;">${body15.fields.TRS}</td>
</tr>
</#list>
</table>
</body>
</html>
