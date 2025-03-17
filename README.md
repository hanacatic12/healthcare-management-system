# Healthcare Management System

## 1. Introduction

This healthcare management system is designed for the purpose of scheduling and managing doctor's appointments from the patient's side, as well as from the doctor's side. It allows for a quick appointment booking process, eliminating the need for going to the hospital in person just to schedule a visit with a doctor. This system also supports cancelling or rescheduling appointments, as well as transferring documents (such as prescriptions or bills).

## 2. Features

### 2.1 Login / register page [#1](https://github.com/hanacatic12/healthcare-management-system/issues/1#issue-2922446771)

The login / register feature lets users create their profile or simply log in (if they already have an account). The user is presented with the login fields, but is redirected to the register page by the 'register' button if they are a first time user. When the user accesses their profile, they are navigated to their profile page.

### 2.2 Appointments page (patient) [#2](https://github.com/hanacatic12/healthcare-management-system/issues/2#issue-2922447943)

The appointments page displays the patient's existing appointments which they can view, cancel or reschedule. The page also has a 'Schedule an appointment' button, which navigates the patient to the appointment scheduling page. 

The patient books an appointment by selecting the hospital ward and their preferred doctor and provides the doctor with information about when they are available for check-up. The doctor's role is to accept or reject that appointment and notify the patient about the exact time of their appointment.
If the patient cannot make it to the scheduled appointment, they can either cancel it or reschedule it.

### 2.3 Profile page [#3](https://github.com/hanacatic12/healthcare-management-system/issues/3#issue-2922982757)

The profile page is the main hub where users access key features. Upon logging in, they see their basic information along with an option to edit their profile. A sidebar menu provides quick navigation to other pages.

**Patient Profile**
Patients can schedule, view, or cancel appointments, access medical documents and prescriptions, check notifications for updates, and log out.

**Doctor Profile**
Doctors can manage appointments, view and update patient records, access a directory of colleagues, send documents and prescriptions, check notifications, and log out.

### 2.4 Appointments page (doctor) [#4](https://github.com/hanacatic12/healthcare-management-system/issues/4#issue-2922985123)

Doctors manage appointment requests by either accepting or rejecting them. When a patient requests an appointment, they include a note with their availability. If the doctor accepts the request, they select the exact date and time based on the patient's availability and notify them. If the request is rejected, the patient is informed, and the request is removed.

### 2.5 Document transfer page [#5](https://github.com/hanacatic12/healthcare-management-system-issues/issues/5)

This feature ensures efficient communication, ensuring a secure transfer of medical information between patients and doctors.

**Patient Document Transfer Page**
Patients should be able to upload necessary medical documents, such as lab results or previous diagnoses. They should also have access to prescriptions and reports provided by their doctors.

**Doctor Document Transfer Page**
Doctors should be able to upload and send medical documents, prescriptions, and test results to their patients. Additionally, they should be able to request specific documents from patients when further review is needed.

## 3. Site Map

![WhatsApp Image 2025-03-17 at 16 17 10_702d8d97](https://github.com/user-attachments/assets/3712aea0-664e-4e62-8310-36ab18e21a87)

## 5. Technical Requirements

The Healthcare Management System is built using the following technologies:

Backend: Java, Spring, PostgreSQL 
Frontend: Angular 
The app Frontend/Backend is hosted on a Netlify/Heroku cloud server respectively.
