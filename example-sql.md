---
layout: default
---
Example SQL Statement
===================
````sql
FROM
	payment,
	pay_method
SELECT
	SUM(payment.amount) AS value,
	COUNT(payment.amount) AS payments
WHERE
	day >= '2014-08-08 00:00:00'
AND
	day <= '2014-08-08 23:59:59'
AND
	payment.pm_id = pay_method.pm_id
AND
	payment.status = 'approved'
AND
	pay_method.type in (
		'ccard',
		'ach',
		'paypal',
		'mail_in',
		'wire',
		'google'
	);
````
