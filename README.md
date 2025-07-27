---

# A/B Test Design: Movie Night Birthday Party Bookings

## Hypothesis

By making the "Book Your Movie Night Birthday Party!" call-to-action more prominent and accessible, we will increase the number of completed booking inquiries.

## Variations

### Control (A)

The current web app design, where the booking form is at the bottom of a long scroll.

### Variation (B)

* **Prominent Call-to-Action (CTA):** Add a sticky "Book Now" button in the header or a floating button that scrolls with the user. When clicked, this button will either scroll the user directly to the form or open a modal containing the booking form.
* **Streamlined Booking Section:** Potentially simplify the form itself or provide a clear progress indicator if it's a multi-step process (though the current form appears single-step). For this A/B test, the primary focus is on accessibility to the form.
* **Visual Cues:** Add subtle animations or visual highlights to the "Book Your Movie Night Birthday Party!" section to draw more attention to it.

---

## Metrics to Track

To measure user engagement and the success of the A/B test, we would track the following:

* **Conversion Rate:**
    * **Primary Metric:** Number of completed booking form submissions / Total unique visitors to the page. This directly measures the effectiveness of the change in leading to the desired action.
* **Click-Through Rate (CTR) on Booking CTA:**
    * Number of clicks on the "Book Now" button (or any new prominent CTA leading to the form) / Total unique visitors to the page. This measures how effectively the new CTA grabs user attention.
* **Time on Page:** Average duration users spend on the page. An increase might indicate more engagement with the content.
* **Scroll Depth:** The percentage of the page users scroll down to. If the new CTA is higher up, this might decrease slightly, but it's important to ensure users still see other valuable content.
* **Bounce Rate:** The percentage of visitors who navigate away from the site after viewing only one page. A lower bounce rate indicates better initial engagement.
* **Form Completion Rate:** For users who start interacting with the form, what percentage complete it? This can help identify form friction points.

---

## Tools for Data Collection and Analysis

### A/B Testing Platform

* **Google Optimize:** This platform allows you to set up experiments, segment users into control and variation groups, serve different versions of your web page, and collect data on how each version performs against your defined metrics. It handles the technical aspects of splitting traffic and tracking.

### Web Analytics

* **Google Analytics 4 (GA4):** Essential for comprehensive data collection. GA4 can track page views, user sessions, engagement events (clicks, scrolls, form submissions), conversion events (e.g., successful form submission), and user demographics. You would configure custom events for the "Book Now" button clicks and form submissions.

### Tag Management System

* **Google Tag Manager (GTM):** Used to easily deploy and manage all your tracking tags (GA4 event tags, A/B testing platform scripts) without needing to modify the website's code directly. This streamlines the implementation of tracking for your A/B test.
