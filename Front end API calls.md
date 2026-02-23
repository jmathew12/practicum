================
Auth

POST /auth/login
File: components/LoginWindow.tsx (line ~54)
Purpose: Authenticate user with credentials

POST /auth/signup
File: app/auth/sign-up/signupApi.tsx (line ~32)
Purpose: Create new user account

POST /auth/forgot-password
File: app/auth/forgot-password/page.tsx (line ~44)
Purpose: Send password reset email

POST /auth/reset-password
File: app/auth/reset-password/page.tsx (line ~134)
Purpose: Reset password using token

POST /auth/change-password
File: app/auth/change-password/changePasswordApi.tsx (line ~29)
Purpose: Change password for logged-in user

================
Users

GET /users/find/:userId
File: app/profile/page.tsx (line ~36)
Purpose: Fetch user profile data

PATCH /users/update/:userId
File: app/edit-user-role-page/page.tsx (line ~134)
File: app/profile/components/EditUserDetailsDialog.tsx (line ~52)
Purpose: Update user role / profile details

================
Events

GET /events
File: components/EventGetter.tsx (line ~11)
Purpose: Fetch list of events

GET /events?{params}
File: utility/queries.ts (lines ~14, ~36)
Purpose: Fetch events with filters/pagination

GET /events/user/:userId?{params}
File: utility/queries.ts (line ~57)
Purpose: Fetch events associated with a user

GET /events/find/:id
File: utility/queries.ts (line ~74)
Purpose: Fetch single event by ID

POST /events/new
File: hooks/useEventForm.tsx (line ~245)
Purpose: Create a new event

PUT /events/update/:eventId
File: hooks/useEditForm.tsx (line ~151)
Purpose: Update existing event

DELETE /events/remove/:id
File: app/event-detail/page.tsx (line ~184)
Purpose: Delete an event

PUT /events/archive/:id
File: components/ArchiveDialog.tsx (line ~29)
Purpose: Archive an event

PUT /events/unarchive/:id
File: components/ArchiveDialog.tsx (line ~29)
Purpose: Unarchive an event

PUT /events/:eventId/cover-image
File: components/CoverPhotoDialog.tsx (line ~43)
Purpose: Upload/update event cover image

================
Event Registration / Attendance

POST /event-registration/attend
File: components/AttendDialog.tsx (line ~82)
Purpose: Register user as attending event

DELETE /event-registration/unattend
File: app/event-detail/page.tsx (line ~382)
File: app/profile/components/AttendedEvents.tsx (line ~198)
Purpose: Unregister user from event

GET /event-registration/user/:userId
File: app/profile/components/AttendedEvents.tsx (line ~145)
Purpose: Fetch events the user attended

GET /event-registration/event/:eventId
File: app/event-detail/page.tsx (line ~294)
Purpose: Fetch users registered for an event

GET /event-registration/check/:eventId/:userId
File: utility/queries.ts (line ~96)
Purpose: Check if user is registered for event

================
Archived Events

GET /events?{params} (archived filter)
File: app/archived-events/page.tsx (line ~110)
Purpose: Fetch archived events with query params

================
API Helpers (Wrappers)

Generic API wrapper functions
File: lib/db.ts

get(endpoint)
post(endpoint, data)
put(endpoint, data)
delete(endpoint)

Purpose: Shared API wrapper used by frontend components

================

Front end API calls

app/archived-events/page.tsx:
109
110: const response = await fetch(`${url}?${params.toString()}`);
111              const data = await response.json();

app/auth/change-password/changePasswordApi.tsx:
28    try {
29: const res = await fetch(`${URL}/auth/change-password`, {
30        method: "POST",

app/auth/forgot-password/page.tsx:
43      // POST request to check for email
44:     const res = await fetch(`${URL}/auth/forgot-password`, {
45        method: "POST",

app/auth/reset-password/page.tsx:
133        // TODO: Implement API call to reset password with token
134:       const res = await fetch(`${URL}/auth/reset-password`, {
135          method: "POST",

app/auth/sign -in/page.tsx:
51        
52:       const res = await fetch(loginEndpoint, {
53          method: "POST",

app/auth/sign-up/signupApi.tsx:
31    try {
32: const response = await fetch(`${apiUrl}/auth/signup`, {
33        method: "POST",

app/edit-user-role-page/page.tsx:
103      try {
104: const res = await fetch(url, {
105          method: "GET",

133        }
134:       const response = await fetch(`${apiUrl}/users/update/${userId}`, {
135          method: "PATCH",

app/event-detail/page.tsx:
183        const apiUrl = process.env.NSC_EVENTS_PUBLIC_API_URL;
184: const response = await fetch(`${apiUrl}/events/remove/${id}`, {
185          method: 'DELETE',

293        const apiUrl = process.env.NSC_EVENTS_PUBLIC_API_URL;
294:       const res = await fetch(`${apiUrl}/event-registration/event/${eventId}`, {
295          headers: {

381        const apiUrl = process.env.NSC_EVENTS_PUBLIC_API_URL;
382:       const response = await fetch(`${apiUrl}/event-registration/unattend`, options);
383        if(!response.ok) {

app/profile/page.tsx:
35      
36:             const response = await fetch(`${URL}/users/find/${userId}`, {
37                  method: "GET",

app/profile/components/AttendedEvents.tsx:
144        try {
145: const res = await fetch(`${URL}/event-registration/user/${userId}`, {
146            headers: {

197      try {
198:       const res = await fetch(`${URL}/event-registration/unattend`, {
199          method: "DELETE",

app/profile/components/EditUserDetailsDialog.tsx:
51        const apiUrl = process.env.NSC_EVENTS_PUBLIC_API_URL;
52:       const response = await fetch(`${apiUrl}/users/update/${user.id}`, {
53          method: 'PATCH',

components/ArchiveDialog.tsx:
28        const endpoint = isArchived ? 'unarchive' : 'archive';
29:       const response = await fetch(`${apiUrl}/events/${endpoint}/${id}`, {
30          method: "PUT",

components/AttendDialog.tsx:
81              const apiUrl = process.env.NSC_EVENTS_PUBLIC_API_URL;
82:             const response = await fetch(`${apiUrl}/event-registration/attend`, options);
83  

components/CoverPhotoDialog.tsx:
42              const apiUrl = process.env.NSC_EVENTS_PUBLIC_API_URL;
43:             const response = await fetch(`${apiUrl}/events/${eventId}/cover-image`, options);
44              if(!response.ok) {

components/EventGetter.tsx:
10  const getEvents = async () => {
11: const response = await fetch(`${URL}/events`);
12      return response.json();

components/LoginWindow.tsx:
53
54: const res = await fetch(`${URL}/auth/login`, {
55                  method: "POST",

hooks/useEditForm.tsx:
150        
151:       const response = await fetch(`${apiUrl}/events/update/${eventId}`, {
152          method: "PUT",

hooks/useEventForm.tsx:
244        const apiUrl = process.env.NEXT_PUBLIC_API_URL || 'http://localhost:3000/api';
245: const response = await fetch(`${apiUrl}/events/new`, {
246          method: "POST",

lib/db.ts:
8    get: async (endpoint: string) => {
9: const response = await fetch(`${API_BASE_URL}${endpoint}`);
10      if (!response.ok) {

16    post: async (endpoint: string, data: any) => {
17: const response = await fetch(`${API_BASE_URL}${endpoint}`, {
18        method: 'POST',

30    put: async(endpoint: string, data: any) => {
31: const response = await fetch(`${API_BASE_URL}${endpoint}`, {
32        method: 'PUT',

44    delete: async(endpoint: string) => {
45: const response = await fetch(`${API_BASE_URL}${endpoint}`, {
46        method: 'DELETE',

utility/queries.ts:
13      });
14: const response = await fetch(`${apiUrl}/events?${params.toString()}`);
15      const data = await response.json();

36: const response = await fetch(`${apiUrl}/events?${String(params)}`);
37      const data = await response.json();

57: const response = await fetch(`${apiUrl}/events/user/${userId}?${String(params)}`);
58      const data = await response.json();

73  const getEventById = async (id: string | null) => {
74: const response = await fetch(`${apiUrl}/events/find/${id}`);
75      const data = await response.json();

95              const token = localStorage.getItem("token");
96: const response = await fetch(`${apiUrl}/event-registration/check/${eventId}/${userId}`, {
97                  headers: {
