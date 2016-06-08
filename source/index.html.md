---
title: API Reference

language_tabs:
  - json

toc_footers:
  - <a href='https://github.com/tripit/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true
---

# Introduction

Welcome to the Loan API!

# Loans

## Get Client info by SSN

```json
{
	"api": "sdf7s8dfysdhf8dsfs", 
	"ssn": "12312312312"
}
```

> The above command returns JSON structured like this:

```json
{
	"result": true, 
	"code": 200, 
	"info": {
		"message": "OK",
		"id" => 645654,
		'ssn' => '12312312312',
		'first_name' => 'John',
		'last_name' => 'Smith',
		'addr_street' => 'Palm Beach street',
		'addr_zip' => '12345',
		'addr_city' => 'New York',
		'tel' => '+1234567890',
		'email' => 'john.smith@example.com',
		'account' => 'String|Account',
		'paper_invoice' => 'Bool',
		'email_invoice' => 'Bool',
		'employer' => 'String',
		'employment' => 'String', // permanent, fixedterm, entrepreneur, student, retired, earlyretirement, illhealthretirement, unemployed
		'employment_start' => 'Date',
		'job_type' => 'String', // employee, upperlevel, lowerlevel, management, entrepreneur, farmer, retired, student, other
		'job_type_other' => 'String',
		'job_title' => 'String',
		'education' => 'String',
		'education_other' => 'String',
		'language' => 'String',
		'gross_income' => 'String',
		'net_income' => 'String',
		'last_year_income' => 'String',
		'expenses' => 'String', 
		'expenses_description' => 'String',
		'loan_expenses' => 'String',
		'living_cost' => 'String',
		'home_ownership' => 'String',
		'home_type' => 'String',
		'second_home' => 'Bool',
		'credit_card' => 'Bool',
		'household_size' => 'Int',
		'dependents' => 'Int',
		'maritalstatus' => 'married',
		'other_factors' => 'Text',
		'other_info' => 'Text',
		'loan_terms_accepted' => 'Bool',
		'data_authorization' => 'Bool'
	}
}
```

This endpoint retrieves information about customer by his SSN number.

### Parameters

Parameter | Description
--------- | -----------
api_key | (required) If empty - user gets json response with error code 401 (unathorized) and message "You have to provide API key".
ssn | (required) If empty - user get json response with error code 401 and message "You have to provide SSN number"

## Post an application

```json
{
	"api": "sdf7s8dfysdhf8dsfs", 
	"ssn": "12312312312", 
	"amount": 1000
}
```

> The above command returns JSON structured like this:

```json
{
	"result": true, 
	code": 201, 
	"info": {
		"message": "OK", 
		"status": "PENDING"
	}
}
```

This endpoint posts an application for a loan to server.

### Parameters

Parameter | Description
--------- | -----------
api | API key
ssn | Customer's SSN code
amount | (integer) An amount of loan

