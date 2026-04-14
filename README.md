# SampleApp-CRUD-Java

A Java sample application demonstrating CRUD operations against QuickBooks Online (QBO) using the Intuit QuickBooks Java SDK.

## Overview

This repository provides a working sample app for performing Create, Read, Query, Update, Delete, and Void operations on many QBO entities. It is intended for learning and exploration of QBO integration patterns, not as a production-ready application.

Key capabilities:
- CRUD examples for QBO entities such as Customer, Invoice, Bill, Payment, Item, Vendor, Employee, JournalEntry and more.
- Uses the Intuit QuickBooks Online Java SDK.
- Includes helper classes for entity construction and QBO service setup.
- Configurable connection settings via `src/main/resources/config.properties`.

## Prerequisites

- Java 1.8
- Maven installed
- Intuit Developer account
- QuickBooks Online app configured on [developer.intuit.com](https://developer.intuit.com)
- Sandbox company connected to your app

## Dependencies

Configured in `pom.xml`:
- `com.intuit.quickbooks-online:ipp-v3-java-devkit:6.5.1`
- `com.intuit.quickbooks-online:ipp-v3-java-data:6.5.1`
- `org.slf4j:slf4j-log4j12:1.7.21`

## Configuration

Update `src/main/resources/config.properties` before running samples.

Example settings:
```properties
# For OAuth2 apps set oauth.type=2
oauth.type=2

oauth2.accessToken=

# Company id or realmId
company.id=
```

- `oauth.type`:
  - `2` for OAuth2
  - `1` for OAuth1 (legacy support)
- `oauth2.accessToken`: OAuth2 access token for your connected QBO company
- `company.id`: realm ID for the QuickBooks company

> For OAuth1 apps, you must also supply the relevant app token, consumer key, consumer secret, access token key, and access token secret. This repository is primarily configured for OAuth2 usage.

## Build

From the project root:
```bash
mvn clean install
```

## Running Samples

Each sample class includes a `main()` method and can be executed independently.

Typical usage:
1. Open a sample class under `src/main/java/com/intuit/developer/sampleapp/crud/entities/<entity>`
2. Run the class as a Java application in your IDE
3. Watch the console output for success messages and returned IDs

### Example sample paths
- `src/main/java/com/intuit/developer/sampleapp/crud/entities/customer/CustomerCreate.java`
- `src/main/java/com/intuit/developer/sampleapp/crud/entities/invoice/InvoiceCreate.java`
- `src/main/java/com/intuit/developer/sampleapp/crud/entities/bill/BillCreate.java`
- `src/main/java/com/intuit/developer/sampleapp/crud/entities/vendor/VendorCreate.java`

## Project Structure

- `src/main/java/com/intuit/developer/sampleapp/crud/entities/`
  - Sample CRUD classes organized by QBO entity
- `src/main/java/com/intuit/developer/sampleapp/crud/helper/`
  - Helper classes and model helpers used by sample flows
- `src/main/java/com/intuit/developer/sampleapp/crud/qbo/`
  - QBO service factory classes
- `src/main/resources/`
  - `config.properties` and supporting configuration files

## Notes

- The sample code focuses on clarity and learning, not full production hardening.
- Some samples assume US locale fields and may require adjustment for other regions.
- Before running attachments or file upload samples, update any local file paths used in the sample.
- If you do not use Maven, import the project into your IDE and add the required SDK jars manually.

## License

This sample is provided for educational purposes and is not intended as a full production solution.

