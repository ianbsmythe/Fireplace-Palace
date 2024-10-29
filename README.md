# The Fireplace Palace

## Project Overview

The **Fireplace Palace** started as a mobile-first landing page built with vanilla **HTML** and **CSS**.  It was aimed at enabling customers of Fireplace Palace to learn more about the company and what they do.  Using **React** and **Next.js**, the site was then refactored to enable design consultations to be booked online via the use of a form; retrieve reviews based on location selection and calling from an API; and find out more about the owners and what they do and stand for in the world of fireplaces.  
The project was based on changing client briefs throughout an agile working week in small groups, implementing these changes to incorporate their needs - finding out about the company, reducing inbound call traffic and managing peak consultation requests more efficiently. The new booking system directs users to a form submission process, enhancing user experience with field validation, loading indicators, and success/error messages.

---

## Features

### Brief Summaries

1. **Initial Landing Page - HTML & CSS**   
   - To build a single page website using only CSS and HTML that matches the designs we were given in a FigJam file.  
   - The site was to be a 'Mobile First' build but it was to respond and change when it hit a desktop screen size (1024px and above) - implement media queries in CSS file.
   - HTML mark-up was to be semantic to support accessibility and SEO.
   - Implement the use of CSS grid, CSS flexbos or a combination of both for the layout.

2. **React Landing Page Refactor**  
   - Have a working React application that looks exactly like the landing page you built already. 
   - The React application needed at least 10 components that came together to make the site look as it should. 
   - Finally, at least some of the components were to be configurable / re-usable  by allowing parent components to pass them *props*.

3. **New Pages/Features with Next.js**
   - Create a 'founders' page that works on a mobile.
   - Implement a menu that works as expected on a mobile.  Be able to click the menu and the full page be covered when the menu appears, and be able to click to close the menu.
   - Incorporate links on the menu and allow for movement between the homepage and founders page. 

4. **A New Component to Fetch Data**
   - Create a new component on the home page that allows a user to select their country and see the latest review from that location.
   - Location click will fetch data from a local JSON file based on England, Scotland and Wales locations.

5. **Design a Consultation/Booking Form**  
   The booking form on the **"Design Booking"** page allows users to fill out their contact details. It includes basic validation to ensure no empty fields, and users receive error messages for missing information before form submission.

4. **Enhanced Booking Form Usability and Validation**  
   The form now includes advanced validation to check for valid phone numbers, emails, and postcodes (using `https://postcodes.io/` API) to ensure only locations in **England**, **Wales**, or **Scotland** are accepted. Specific error messages appear for any fields that fail validation, and a success message displays upon successful submission.

---

## Installation

1. Clone the repository:
   ```bash
   git clone <repository-url>
2. Navigate to the project directory:
   ```bash
   cd fireplace-palace
3. Install dependencies:
   ```bash
   npm install
4. Start the development server:
   ```bash
   npm run dev
   
---

## Detailed Feature Breakdown

1. **Book Consultation Button**
   - Objective: Replace the homepage phone number with a "Book Consultation" button to redirect users to a new booking page.
   - Implementation:
     - Remove the phone number from the homepage.
     - Add a new "Book Consultation" button.
     - Link the button to the /booking page where the form is displayed.

2. **Reviews by Country Component**
   - Objective: Display customer reviews by country to provide social proof.
   - Implementation:
     - Create a Reviews component with a dropdown or buttons for country selection.
     - Fetch reviews based on the selected country using the API: `GET https://seal-app-336e8.ondigitalocean.app/reviews?country={country}`
     - Display the latest review dynamically.

3. **Design Booking Form with Basic Validation**
   - Objective: Allow users to submit their booking requests by filling out the form on the "Design Booking" page.
   - Implementation:
     - Create a new ContactForm component with necessary input fields.
     - Use useState to manage form field values.
     - Validate fields to ensure no empty inputs before submission.
     - Display errors if fields are missing.

4. **Enhanced Usability & Advanced Validation with useReducer**
   - Objective: Improve form usability with loading states and specific error messages, validate emails, phone numbers, and restrict bookings to UK regions.
   - Implementation:
     - Refactor useState to useReducer for complex state management.
     - Add loading state to indicate form submission is in progress.
     - Validate phone numbers, emails, and use https://postcodes.io/ API to check postcodes for eligible regions.
     - Show specific error messages for each field, such as:
       - Phone number: "Not a valid phone number."
       - Email: "Not a valid email address."
       - Postcode: "No bookings outside of England, Wales, or Scotland."
     - Display a success message upon successful form submission and hide the form.

## Code Snippets

Please refer to the provided document for the code snippets related to the Reducer, Form Field Update Handler, and Form Submission Handler with Validation.

## API References

- Reviews API: `GET https://seal-app-336e8.ondigitalocean.app/reviews?country={country}`
- Postcode Validation: `https://postcodes.io/`

## Notes

- Postcode Validation: Only accepts England, Wales, and Scotland.
- Loading State: The form displays "Submitting..." on the submit button during form submission.