SELECT
NewRunsheetCode,
Code,
bas.MaterialCname,
RequiredPackCount as '需求箱数',
RequiredPartCount as '需求件数',
ActualPackCount as '实际箱数',
ActualPartCount as '实际件数',
WorkNo,
twd.CreateTime
FROM
	TWD_Runsheet twd
	LEFT JOIN TWD_RunsheetDetail run ON twd.id= run.RunsheetID
	LEFT JOIN BAS_MaterialBase bas ON run.MaterialID = bas.ID 
WHERE
	Code = '4873364'
	ORDER BY CreateTime