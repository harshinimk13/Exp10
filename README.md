# Experiment 10 – Data Sharing Using Contacts Content Provider

## Aim

To develop an Android application that demonstrates data sharing using the Contacts Content Provider to retrieve and display contact names and phone numbers stored on the device.

## Overview

The Contacts Provider application demonstrates how an Android application can access contact information using the Android Contacts Content Provider.

The application requests permission to access contacts, retrieves contact names and phone numbers using ContentResolver, and displays the retrieved information in a ListView.

The application also provides a user-friendly interface with the student's details.

## Objectives

1. To understand the Android Contacts Content Provider.
2. To request runtime permission to access device contacts.
3. To retrieve contact names and phone numbers using ContentResolver.
4. To read contact information using Cursor.
5. To display contact details using ListView and ArrayAdapter.
6. To understand data sharing between Android applications using Content Providers.

## Technologies Used

- **Programming Language:** Kotlin
- **Development Environment:** Android Studio
- **User Interface:** XML
- **Data Access:** Android Contacts Content Provider
- **Content Resolver:** Used to retrieve contact information
- **UI Components:** ListView, ArrayAdapter, Button, TextView
- **Permission Handling:** Android Runtime Permissions
- **Android API:** ContactsContract

## Features

- **Runtime Permission:** Requests permission to access device contacts.
- **Contact Retrieval:** Retrieves contact names and phone numbers from the device.
- **Contact Display:** Displays retrieved contacts in a ListView.
- **Content Resolver:** Uses ContentResolver to access contact information.
- **User-Friendly Interface:** Displays student details with an attractive interface.
- **Permission Handling:** Checks permission before accessing contacts.
- **Dynamic Loading:** Loads contacts when the user clicks the Load Contacts button.

## Project Structure

```text
ContactsProvider/
├── app/
│   └── src/
│       └── main/
│           ├── java/com/example/contactsprovider/
│           │   └── MainActivity.kt
│           ├── res/
│           │   ├── layout/
│           │   │   └── activity_main.xml
│           │   └── values/
│           │       ├── colors.xml
│           │       ├── strings.xml
│           │       └── themes.xml
│           └── AndroidManifest.xml
├── build.gradle.kts
├── settings.gradle.kts
└── README.md
```

## Required Permissions

The application requires the `READ_CONTACTS` permission to access contact names and phone numbers stored on the device.

### Permission Declaration

Add the following permission to `AndroidManifest.xml`, outside the `<application>` tag:

```xml
<uses-permission android:name="android.permission.READ_CONTACTS" />
```

The application requests runtime permission from the user before accessing contacts.

**Privacy Note:** Contact information is accessed only after the user grants the required permission.

## Implementation Details

The application is developed using Kotlin in Android Studio with an XML-based user interface.

### 1. Permission Handling
The application requests the `READ_CONTACTS` runtime permission before accessing the device's contacts.

### 2. Accessing Contacts
The `ContentResolver` queries the Android Contacts Content Provider using `ContactsContract.CommonDataKinds.Phone.CONTENT_URI`.

### 3. Retrieving Contact Information
A `Cursor` retrieves contact names and phone numbers from the query results.

### 4. Displaying Contacts
The retrieved contact information is stored in a list and displayed using a `ListView` with an `ArrayAdapter`.

### 5. User Interaction
The user clicks the **Load Contacts** button to retrieve and display contacts after granting permission.

## Application Workflow

1. Launch the Contacts Provider application.
2. The home screen displays the application interface and student details.
3. Click the **Load Contacts** button.
4. The application requests permission to access contacts if permission has not already been granted.
5. Grant the `READ_CONTACTS` permission.
6. The application retrieves contact names and phone numbers using `ContentResolver`.
7. The retrieved contacts are displayed in a `ListView`.
8. If permission is denied, the application handles the situation appropriately.

### Workflow Summary

Launch App → Request Permission → Access Contacts Provider → Retrieve Contact Details → Display Contacts

## Testing and Test Cases

The application is tested to verify that contact permissions are handled correctly and contact information is retrieved and displayed as expected.

| Test Case | Test Scenario | Expected Result | Status |
|---|---|---|---|
| TC01 | Launch the application | Home screen is displayed successfully | Verify |
| TC02 | Click Load Contacts without permission | Permission request is displayed | Verify |
| TC03 | Grant contact permission | Application accesses the contacts | Verify |
| TC04 | Load contacts | Contact names and phone numbers are displayed | Verify |
| TC05 | Deny contact permission | Application handles the denied permission | Verify |
| TC06 | No contacts are available | Application handles the empty contact list | Verify |

**Note:** Update the status to **Pass** or **Fail** after testing each case on your device or emulator.

## Screenshots

The following screenshots demonstrate the output of the Contacts Provider application.

### Output 1: Application Home Screen

Displays the application interface and student details.

![Output 1](Screenshots/Output%201.png)

### Output 2: Contacts Display

Shows the output of the application when accessing and displaying contact information.

![Output 2](Screenshots/Output%202.png)

## Concepts Learned

Through this experiment, the following concepts were learned:

1. Understanding the Android Contacts Content Provider.
2. Accessing contact information using `ContactsContract`.
3. Retrieving data using `ContentResolver`.
4. Reading query results using `Cursor`.
5. Implementing runtime permissions in Android.
6. Displaying dynamic data using `ListView` and `ArrayAdapter`.
7. Understanding data sharing between Android applications through Content Providers.
8. Handling permission denial and empty contact lists.

## Result

Thus, the Android application was successfully developed to demonstrate data sharing using the Contacts Content Provider. The application retrieves contact names and phone numbers with the user's permission and displays the retrieved information using a ListView.
