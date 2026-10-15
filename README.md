# Experiment 10 – Data Sharing Using Contacts Content Provider

## Aim

To develop an Android application that demonstrates data sharing using the Contacts Content Provider to retrieve and display contact names and phone numbers stored on the device.

## Overview

The Contacts Provider application demonstrates how Android applications can access contact information using the Android Contacts Content Provider.

The application requests permission to access contacts, retrieves contact names and phone numbers using `ContentResolver`, and displays the retrieved information in a `ListView`.

The application also includes an attractive user interface displaying the student's name and USN.

## Objectives

1. To understand the Android Contacts Content Provider.
2. To request runtime permission to access device contacts.
3. To retrieve contact names and phone numbers using `ContentResolver`.
4. To display contact information using a `ListView`.
5. To understand how Android applications share data through Content Providers.

## Technologies Used

- **Programming Language:** Kotlin
- **Development Environment:** Android Studio
- **User Interface:** XML
- **Data Access:** Android Contacts Content Provider
- **Content Resolver:** Used to retrieve contact information
- **UI Components:** ListView, ArrayAdapter, Button, TextView
- **Permission Handling:** Android Runtime Permissions
- **API:** Android ContactsContract API

## Features

- **Runtime Permission:** Requests permission from the user to access device contacts.
- **Contact Retrieval:** Retrieves contact names and phone numbers from the device.
- **Contact Display:** Displays retrieved contacts in a ListView.
- **Content Resolver:** Uses ContentResolver to access contact data.
- **User-Friendly Interface:** Provides an attractive interface with student details.
- **Permission Handling:** Handles contact access permission before retrieving data.
- **Dynamic Data Loading:** Loads contacts when the user clicks the Load Contacts button.

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

## Required Permissions

The application requires the `READ_CONTACTS` permission to access contact names and phone numbers stored on the device.

Permission declaration in `AndroidManifest.xml`:

```xml
<uses-permission android:name="android.permission.READ_CONTACTS" />
```

## Implementation Details

The application is developed using Kotlin in Android Studio with an XML-based user interface.

### 1. Permission Handling
The application requests the `READ_CONTACTS` runtime permission before accessing the device's contacts.

### 2. Accessing Contacts
The `ContentResolver` is used to query the Android Contacts Content Provider through `ContactsContract.CommonDataKinds.Phone.CONTENT_URI`.

### 3. Retrieving Contact Information
A `Cursor` retrieves the contact names and phone numbers from the query results.

### 4. Displaying Contacts
The retrieved contact information is stored in a list and displayed using a `ListView` with an `ArrayAdapter`.

### 5. User Interaction
The user clicks the **Load Contacts** button to retrieve and display the contacts after granting permission.

## Application Workflow

1. Launch the Contacts Provider application.
2. The application displays the home screen with student details.
3. Click the **Load Contacts** button.
4. The application requests permission to access contacts if permission has not already been granted.
5. Grant the `READ_CONTACTS` permission.
6. The application retrieves contact names and phone numbers using `ContentResolver`.
7. The retrieved contacts are displayed in a `ListView`.
8. If permission is denied, the application should handle the situation appropriately.

### Workflow Summary

Launch App → Request Permission → Access Contacts Provider → Retrieve Contact Details → Display Contacts

## Testing and Test Cases

The application was tested to verify that contact permissions are handled correctly and contact information is retrieved and displayed as expected.

| Test Case | Test Scenario | Expected Result | Status |
|---|---|---|---|
| TC01 | Launch the application | Home screen is displayed successfully | Pass |
| TC02 | Click the Load Contacts button | Permission is requested if not already granted | Pass |
| TC03 | Grant contact permission | Application accesses the contacts | Pass |
| TC04 | Load contacts | Contact names and phone numbers are displayed | Pass |
| TC05 | Deny contact permission | Application handles the denied permission appropriately | Pass |
| TC06 | Load contacts when no contacts are available | Application handles the empty contact list appropriately | Pass |

**Note:** Mark each test case as Pass only after verifying the behavior on your device or emulator.

## Screenshots

The following screenshots demonstrate the working of the Contacts Provider application.

### 1. Home Screen
Displays the application interface with the student's name and details.

![Home Screen](Screenshots/HomeScreen.png)

### 2. Contact Permission
Displays the permission request when the application attempts to access contacts.

![Contact Permission](Screenshots/Permission.png)

### 3. Contact List
Displays the retrieved contact names and phone numbers.

![Contact List](Screenshots/ContactList.png)

## Concepts Learned

Through this experiment, the following concepts were learned:

1. Understanding the Android Contacts Content Provider.
2. Accessing device contacts using `ContactsContract`.
3. Using `ContentResolver` to retrieve contact information.
4. Working with `Cursor` to read query results.
5. Implementing runtime permissions in Android.
6. Displaying dynamic data using `ListView` and `ArrayAdapter`.
7. Understanding data sharing between Android applications through Content Providers.
8. Handling permission denial and empty contact lists.

## Result

Thus, the Android application was successfully developed to demonstrate data sharing using the Contacts Content Provider. The application retrieves contact names and phone numbers with the user's permission and displays them using a ListView.
