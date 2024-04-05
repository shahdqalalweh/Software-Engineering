# Software-Engineering
# Chapter 2: The Entity Relationship Data Model
# 2-1-1 Entities:
To make our database ER diagram simpler to understand, we have divided the  entities into several functional groups:
•	User Management: Students, UserAccounts, Admins
•	Course Management: Courses, Centers, CourseMaterials, CourseSchedule
•	Enrollment & Feedback: Enrollments, CourseReviews, Feedback
•	Scheduling & Events: CourseSchedule, Events
•	Notifications & Communications: Notifications
•	Financial Transactions: Payments, Wishlist
# 2-1-2 Entities Description:

Students: Represents individuals enrolled in the academic center. Holds personal information, academic major, and enrollment status.
Courses: Contains details of courses offered, including name, associated department, credit value, and related materials like syllabus.
Centers: Details the centers or departments within the academic center, including the courses they offer and a bio for the center.
Enrollments: Tracks the registration of students in courses, including the semester, grades received, and current status.
CourseSchedule: Manages when and where courses are held, detailing the weekly schedule and location.
CourseReviews: Allows students to rate and comment on courses, providing feedback and insights for future students.
UserAccounts: Manages login credentials and roles for users of the database system, including last login tracking.
Wishlist: Enables students to list courses they wish to take in the future, helping with planning and course demand forecasting.
Notifications: Sends messages to users, such as reminders or alerts, and tracks whether they have been read.
Payments: Handles financial transactions related to course enrollments, including payment amounts and methods.
Feedback: Collects general feedback from users on various subjects related to the academic center.
Admins: Represents administrative staff, with their contact information and role within the academic center.
CourseMaterials: Stores information about educational content provided for courses, including type and upload date.
Events: Details events hosted by the academic center, including descriptions and scheduling.
# 2-2 Entities & Attributes:
1.	Students
o	StudentID (PK)
o	FirstName
o	LastName
o	Email
o	PasswordHash
o	Major
o	EnrollmentStatus

2.	Courses
o	CourseID (PK)
o	CourseName
o	CenterID (FK)
o	Credits
o	Description
o	Syllabus
o	ScheduleID (FK)

3.	Centers
o	CenterID (PK)
o	Name
o	Email
o	Bio
o	CoursesTaught

4.	Enrollments
o	EnrollmentID (PK)
o	StudentID (FK)
o	CourseID (FK)
o	Semester
o	Grade
o	Status

5.	CourseSchedule
o	ScheduleID (PK)
o	CourseID (FK)
o	DayOfWeek
o	StartTime
o	EndTime
o	Location
6.	CourseReviews
o	ReviewID (PK)
o	CourseID (FK)
o	StudentID (FK)
o	Rating
o	Comment
o	DatePosted

7.	UserAccounts
o	UserID (PK)
o	Username
o	PasswordHash
o	LastLogin
o	Role

8.	Wishlist
o	WishlistID (PK)
o	StudentID (FK)
o	CourseID (FK)
o	DateAdded

9.	Notifications
o	NotificationID (PK)
o	UserID (FK)
o	Message
o	DateSent
o	IsRead

10.	Payments
o	PaymentID (PK)
o	EnrollmentID (FK)
o	Amount
o	DatePaid
o	PaymentMethod

11.	Feedback
o	FeedbackID (PK)
o	UserID (FK)
o	Subject
o	Message
o	DateReceived
12.	Admins
o	AdminID (PK)
o	FirstName
o	LastName
o	Email
o	Role

13.	CourseMaterials
o	MaterialID (PK)
o	CourseID (FK)
o	Title
o	Description
o	FileType
o	UploadDate

14.	Events
o	EventID (PK)
o	Title
o	Description
o	StartDate
o	EndDate
# 2-3 Relationships:
•	Students to Enrollments: A student can have multiple enrollments.
•	Courses to Enrollments: A course can have multiple students enrolled.
•	Centers to Courses: A center offers multiple courses.
•	CourseSchedule to Courses: Each course has a schedule.
•	CourseReviews to Courses: A course can have multiple reviews.
•	CourseReviews to Students: A student can write multiple reviews.
•	UserAccounts to Students/Admins: A user account is linked to a student or an admin.
•	Wishlist to Students: A student can have multiple wishlist entries.
•	Notifications to UserAccounts: A user account can receive multiple notifications.
•	Payments to Enrollments: Each enrollment has a payment record.
•	Feedback to UserAccounts: A user can submit multiple feedback entries.
•	CourseMaterials to Courses: A course can have multiple materials.
•	Events: Standalone entity for events.



