## MySQL Database Design
### Table: doctors
- id: INT, Primary Key, Auto Increment
- name: VARCHAR(100), Not Null
- email: VARCHAR(100), Not Null, Unique
- password: VARCHAR(255), Not Null
- phone: VARCHAR(15), Nullable
- specialization: VARCHAR(100), Nullable
- availability: TEXT or JSON, Nullable
- created_at: TIMESTAMP, Default CURRENT_TIMESTAMP

### Table: patients
- id: INT, Primary Key, Auto Increment
- name: VARCHAR(100), Not Null
- email: VARCHAR(100), Not Null, Unique
- password: VARCHAR(255), Not Null
- phone: VARCHAR(15), Nullable
- dob: DATE, Nullable
- gender: VARCHAR(10), Nullable
- created_at: TIMESTAMP, Default CURRENT_TIMESTAMP
  
### Table: appointments
- id: INT, Primary Key, Auto Increment
- doctor_id: INT, Foreign Key → doctors(id)
- patient_id: INT, Foreign Key → patients(id)
- appointment_time: DATETIME, Not Null
- status: INT (0 = Scheduled, 1 = Completed, 2 = Cancelled)

### Table: appointments
- id: INT, Primary Key, Auto Increment
- name: VARCHAR(100), Not Null
- email: VARCHAR(100), Not Null, Unique
- password: VARCHAR(255), Not Null
- created_at: TIMESTAMP, Default CURRENT_TIMESTAMP

  ## MongoDB Collection Design
  {
  "_id": { "$oid": "6653e9fd5e9b1b1d9c3e9e21" },
  "appointmentId": 51,
  "patientId": 12,
  "doctorId": 7,
  "prescribedAt": "2025-06-01T10:30:00Z",
  "medications": [
    {
      "name": "Paracetamol",
      "dosage": "500mg",
      "instructions": "Take 1 tablet every 6 hours after meals",
      "duration": "5 days"
    },
    {
      "name": "Ibuprofen",
      "dosage": "200mg",
      "instructions": "Take only if pain persists",
      "duration": "As needed"
    }
  ],
  "doctorNotes": "Patient recovering well. Monitor temperature daily.",
  "tags": ["fever", "pain relief", "OTC"],
  "refillPolicy": {
    "refillAllowed": true,
    "maxRefills": 2,
    "lastRefillDate": "2025-06-02T08:00:00Z"
  },
  "pharmacy": {
    "name": "City Meds",
    "location": "Downtown Clinic Building"
  },
  "metadata": {
    "createdBy": "dr_adams",
    "createdOn": "2025-06-01T10:35:00Z",
    "modifiedOn": "2025-06-02T09:00:00Z",
    "version": 1
  }
}
