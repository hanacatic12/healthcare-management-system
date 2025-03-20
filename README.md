# Healthcare Management System

## 1. Introduction

This healthcare management system is designed for the purpose of scheduling and managing doctor's appointments from the patient's side, as well as from the doctor's side. It allows for a quick appointment booking process, eliminating the need for going to the hospital in person just to schedule a visit with a doctor. This system also supports cancelling or rescheduling appointments, as well as transferring documents (such as prescriptions or bills).

## 2. Features

### 2.1 Login / register page [#1](https://github.com/hanacatic12/healthcare-management-system/issues/1#issue-2922446771)

The login / register feature lets users create their profile or simply log in (if they already have an account). The user is presented with the login fields, but is redirected to the register page by the 'register' button if they are a first time user. When the user accesses their profile, they are navigated to their profile page.
However, the register feature is created only for patients. The doctors will already be inserted into the database, since we don't want random people creating doctor profiles.

![Screenshot 2025-03-20 125817](https://github.com/user-attachments/assets/4a5d060b-089c-4234-9a7d-9f95215c10ad)

### 2.2 Appointments page (patient) [#2](https://github.com/hanacatic12/healthcare-management-system/issues/2#issue-2922447943)

The appointments page displays the patient's existing appointments which they can view, cancel or reschedule. The page also has a 'Schedule an appointment' button, which navigates the patient to the appointment scheduling page. 

The patient books an appointment by selecting the hospital ward and their preferred doctor and provides the doctor with information about when they are available for check-up. The doctor's role is to accept or reject that appointment and notify the patient about the exact time of their appointment.
If the patient cannot make it to the scheduled appointment, they can either cancel it or reschedule it.

![Screenshot 2025-03-20 130203](https://github.com/user-attachments/assets/b448b8a9-eb85-4734-8304-7adbc99773a6)

### 2.3 Profile page [#3](https://github.com/hanacatic12/healthcare-management-system/issues/3#issue-2922982757)

The profile page is the main hub where users access key features. Upon logging in, they see their basic information along with an option to edit their profile. A sidebar menu provides quick navigation to other pages.

#### **Patient Profile**
Patients can schedule, view, or cancel appointments, access medical documents and prescriptions, and log out.

#### **Doctor Profile**
Doctors can manage appointments, view and update patient information, send documents and prescriptions, and log out.

![Screenshot 2025-03-20 130525](https://github.com/user-attachments/assets/0dcf0054-083b-41ae-b194-afbfc804c4f3)

### 2.4 Appointments page (doctor) [#4](https://github.com/hanacatic12/healthcare-management-system/issues/4#issue-2922985123)

Doctors manage appointment requests by either accepting or rejecting them. When a patient requests an appointment, they include a note with their availability. If the doctor accepts the request, they select the exact date and time based on the patient's availability and notify them. If the request is rejected, the patient is informed, and the request is removed.

![Screenshot 2025-03-20 130617](https://github.com/user-attachments/assets/644f4feb-3238-4aef-89f5-11a44c75fd3b)

### 2.5 Document transfer page [#5](https://github.com/hanacatic12/healthcare-management-system-issues/issues/5)

This feature ensures efficient communication, ensuring a secure transfer of medical information between patients and doctors.

**Patient Document Transfer Page**
Patients should be able to upload necessary medical documents, such as lab results or previous diagnoses. They should also have access to prescriptions and reports provided by their doctors.

**Doctor Document Transfer Page**
Doctors should be able to upload and send medical documents, prescriptions, and test results to their patients. Additionally, they should be able to download specific documents from patients when further review is needed.

![Screenshot 2025-03-20 130844](https://github.com/user-attachments/assets/ed8fbf7e-c5e6-4c46-ae10-3540723a62d0)

### 2.6 Patient page (doctor) [#6](https://github.com/hanacatic12/healthcare-management-system-issues/issues/6)

Doctors can easily search for their patients and view general information, including basic details and the patient’s current diagnosis. This page helps doctors quickly access important information and provides a clear overview of each patient. Additionally, doctors can update diagnoses by adding new ones or removing those from which the patient has recovered, ensuring that records remain accurate and up to date.

![Screenshot 2025-03-20 130955](https://github.com/user-attachments/assets/bfa91167-118f-4b6d-b019-79e99b9b65b7)

## 3. Site Map

![alt text](https://github.com/hanacatic12/healthcare-management-system-issues/blob/main/HealthcareManagementSystemSiteMap.png?raw=true)

## 4. API documentation

### 4.1. API Endpoints

| #  | CRUD    | URL Path                          | Request         | Response         | Description                                      | Functionality |
|----|---------|----------------------------------|----------------|-----------------|--------------------------------------------------|--------------|
| I.a | Login   | /login                           | LoginDto       | LoginDto       | Authenticates a user.                           | 2.1          |
| I.b | Create  | /register                        | RegisterDto    | RegisterDto    | Registers a new patient.                        | 2.1          |
| I.c | Read    | /user/{uid}                      | -              | UserDto        | Retrieves profile details of a user.            | 2.3          |
| I.d | Update  | /user/{uid}                      | UserDto        | UserDto        | Updates profile information of a user.          | 2.3          |
| II.a | Create | /appointments/{uid}              | AppointmentDto | AppointmentDto | Books a new appointment.                        | 2.2, 2.4     |
| II.b | Read   | /appointments/{uid}              | -              | List AppointmentDto | Retrieves all upcoming appointments of a user. | 2.2, 2.4     |
| II.c | Read   | /appointments/{uid}/{aid}        | -              | AppointmentDto | Retrieves a specific appointment.               | 2.2, 2.4     |
| II.d | Update | /appointments/{uid}              | AppointmentDto | AppointmentDto | Updates an appointment (accepting, rescheduling, canceling). | 2.2, 2.4 |
| III.a | Read  | /patients/{uid}                  | -              | List UserDto  | Retrieves all patients.                         | 2.6          |
| III.b | Read  | /patients/{uid}/{uid}            | -              | UserDto        | Retrieves details of a specific patient.        | 2.6          |
| III.c | Update | /patients/{uid}                  | StatusDto      | StatusDto      | Updates patient status (accept, reject).        | 2.6          |
| IV.a | Create | /documents/{uid}                 | DocumentDto    | DocumentDto    | Uploads a new document (prescription, labs, etc.). | 2.5      |
| IV.b | Read   | /documents/{uid}                 | -              | List DocumentDto | Retrieves all documents of a user.             | 2.5          |
| IV.c | Read   | /documents/{uid}/{did}           | -              | DocumentDto    | Retrieves a specific document.                  | 2.5          |

### 4.2. Data Transfer Objects

```
LoginDto
{
  "email": string,
  "password": string 
}
```

```
RegisterDto 
{
  "fname": string,
  "lname": string,
  "email": string,
  "password": string,
  "phone": string,
  "address": string,
  "city": string,
  "DOB": date,
  "gender": string,
  "blood_group": string
}
```

```
UserDto
{
  "uid": number,
  "name": string,
  "email": string,
  "password": string,
  "phone": string,
  "address": string,
  "city": string,
  "DOB": date,
  "gender": string,
  "blood_group": string,
  "last_visit": string,
  "department": string,
  "work_start": time,
"work_end": time
}
```

```
AppointmentDto 
{
  "aid": number,
  "patientId": number,
  "doctorId": number,
  "room": number,
  "note": string,
  "date": date,
  "time": time,
  "status": string
}
```

```
StatusDto 
{
  "patientId": number,
  "doctorId": number,
  "status": string
}
```

```
DocumentDto 
{
  "did": number,
  "uid": number,
  "documentType": string,
  "fileName": string,
}
```

## 5. Technical Requirements

The Healthcare Management System is built using the following technologies:

Backend: Java, Spring, PostgreSQL 
Frontend: Angular 
The app Frontend/Backend is hosted on a Netlify/Heroku cloud server respectively.
