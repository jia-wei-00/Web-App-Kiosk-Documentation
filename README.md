1\. Front-End Coding Task:
--------------------------

*   **Repository:** [https://github.com/jia-wei-00/web-app-kiosk](https://github.com/jia-wei-00/web-app-kiosk)
*   **Link:** [**https://web-app-kiosk.vercel.app/**](https://web-app-kiosk.vercel.app/)
    

2\. UI/UX Design Challenge:
---------------------------

*   **Figma:** [https://www.figma.com/design/HBOjfF5cLErqUQNYDpRlTk/Untitled?node-id=0-1&t=JOwQXc3viskaetGJ-1](https://www.figma.com/design/HBOjfF5cLErqUQNYDpRlTk/Untitled?node-id=0-1&t=JOwQXc3viskaetGJ-1)
*   **Figma:** [https://hungry-flee-93382112.figma.site](https://hungry-flee-93382112.figma.site)

3\. A/B Test Design:
--------------------

Hypothesis

By making the "Book Your Movie Night Birthday Party!" call-to-action more prominent and accessible, we will increase the number of completed booking inquiries.

Variations

### Control (A)

The current web app design, where the booking form is at the bottom of a long scroll.

### Variation (B)

*   **Prominent Call-to-Action (CTA):** Add a sticky "Book Now" button in the header or a floating button that scrolls with the user. When clicked, this button will either scroll the user directly to the form or open a modal containing the booking form.
    
*   **Streamlined Booking Section:** Potentially simplify the form itself or provide a clear progress indicator if it's a multi-step process (though the current form appears single-step). For this A/B test, the primary focus is on accessibility to the form.
    
*   **Visual Cues:** Add subtle animations or visual highlights to the "Book Your Movie Night Birthday Party!" section to draw more attention to it.
    

Metrics to Track

To measure user engagement and the success of the A/B test, we would track the following:

*   Conversion Rate:
    
    *   **Primary Metric:** Number of completed booking form submissions / Total unique visitors to the page. This directly measures the effectiveness of the change in leading to the desired action.
        
*   Click-Through Rate (CTR) on Booking CTA:
    
    *   Number of clicks on the "Book Now" button (or any new prominent CTA leading to the form) / Total unique visitors to the page. This measures how effectively the new CTA grabs user attention.
        
*   **Time on Page:** Average duration users spend on the page. An increase might indicate more engagement with the content.
    
*   **Scroll Depth:** The percentage of the page users scroll down to. If the new CTA is higher up, this might decrease slightly, but it's important to ensure users still see other valuable content.
    
*   **Bounce Rate:** The percentage of visitors who navigate away from the site after viewing only one page. A lower bounce rate indicates better initial engagement.
    
*   **Form Completion Rate:** For users who start interacting with the form, what percentage complete it? This can help identify form friction points.
    

**Tools for Data Collection and Analysis**

A/B Testing Platform

*   **Google Optimize:** This platform allows you to set up experiments, segment users into control and variation groups, serve different versions of the web page, and collect data on how each version performs against defined metrics. It handles the technical aspects of splitting traffic and tracking.
    

Web Analytics

*   **Google Analytics:** Essential for comprehensive data collection. GA4 can track page views, user sessions, engagement events (clicks, scrolls, form submissions), conversion events (e.g., successful form submission), and user demographics. You would configure custom events for the "Book Now" button clicks and form submissions.
    

Tag Management System

*   **Google Tag Manager (GTM):** Used to easily deploy and manage all tracking tags without needing to modify the website's code directly. This streamlines the implementation of tracking for A/B test.
    

4\. Problem-Solving Scenario (Written Response):
------------------------------------------------

I. Diagnosis: Identifying the Root Causes

Before optimizing, you need to understand what is causing the slowness.

1.  **Performance Audits with Developer Tools:**
    
    *   **Google Lighthouse:** Run Lighthouse audits (within Chrome Developer Tools or online at PageSpeed Insights) on web app, specifically on mobile simulations (e.g., set network throttling to "Slow 3G" and CPU throttling to "4x slowdown"). Pay close attention to:
        
        *   **First Contentful Paint (FCP):** When the first text or image is painted.
            
        *   **Largest Contentful Paint (LCP):** When the largest content element in the viewport becomes visible.
            
        *   **Total Blocking Time (TBT):** Sum of all time periods between FCP and TTI where the main thread was blocked.
            
        *   **Cumulative Layout Shift (CLS):** Measures visual stability.
            
        *   **Performance Score:** Overall score.
            
    *   **Chrome DevTools (Performance Tab):**
        
        *   **Record a performance profile:** Simulate a mobile device (responsive design mode) and throttle the network/CPU. Record a load of the app.
            
        *   **Analyze the waterfall:** Look for long-running scripts, large assets, excessive network requests, and blocking resources.
            
        *   **Identify long tasks:** See if any JavaScript tasks are blocking the main thread for extended periods
            
2.  **Network Analysis:**
    
    *   **Network Tab (DevTools):** Observe the size and number of requests. Look for uncompressed assets, large images, and numerous HTTP requests.
        
    *   **Simulate various network conditions:** Test on different mobile network speeds to understand how latency and bandwidth affect performance.
        
3.  **Real User Monitoring (RUM) Tools:**
    
    *   Use Datadog to track metrics like page load time, resource loading times, and API response times for actual users.
        
4.  **Device Testing:**
    
    *   **Test on actual mobile devices:** Don't rely solely on emulators/simulators. Test on a range of devices (old, new, low-end, high-end) and operating systems (Android, iOS) to identify device-specific issues.
        
    *   **BrowserStack :** Use cloud-based testing platforms to access a wide array of real devices and browsers.
        

**II. Optimization Strategies**

Once you've identified the culprits, apply these optimization techniques:

A. Front-End Optimizations

1.  **Image Optimization:**
    
    *   **Compress Images:** Use tools like TinyPNG, ImageOptim, or online compressors to reduce file sizes without sacrificing quality.
        
    *   **Responsive Images:** Serve different image sizes for different screen resolutions using srcset and sizes attributes in  tags or  elements.
        
    *   **Next-gen Formats:** Use modern image formats like WebP (and AVIF where supported) which offer better compression than JPEG or PNG.
        
    *   **Lazy Loading:** Implement lazy loading for images and other media (e.g., using loading="lazy" attribute or Intersection Observer API) so they only load when they enter the viewport.
        
2.  **CSS Optimization:**
    
    *   **Minify and Compress:** Remove unnecessary characters (whitespace, comments) and compress CSS files.
        
    *   **Remove Unused CSS (Tree Shaking):** Use tools like PurgeCSS to remove CSS rules that are not used on a given page.
        
    *   **Avoid @import:** Use  tags instead of @import in CSS files, as @import can block parallel downloads.
        
3.  **JavaScript Optimization:**
    
    *   **Minify and Compress:** Similar to CSS, minify and compress JavaScript files.
        
    *   **Code Splitting:** Break down large JavaScript bundles into smaller chunks that are loaded on demand. This is particularly useful for single-page applications (SPAs).
        
    *   **Tree Shaking:** Remove unused JavaScript code.
        
    *   **Optimize Third-Party Scripts:** Evaluate the impact of third-party scripts (analytics, ads, widgets) and lazy-load them if possible.
        

B. Server-Side and Network Optimizations

1.  **Leverage Caching:**
    
    *   **Browser Caching:** Set appropriate Cache-Control headers for static assets so browsers can store them locally and reduce repeat downloads.
        
    *   **CDN (Content Delivery Network):** Use a CDN to serve static assets from geographically closer servers to users, reducing latency.
        
2.  **Optimize Server Response Times:**
    
    *   **Database Optimization:** Optimize database queries, use appropriate indexing, and consider denormalization for frequently read data.
        
    *   **Backend Code Optimization:** Review and optimize server-side code for efficiency.
        
    *   **Load Balancing:** If traffic is high, distribute requests across multiple servers.
        

**III. Continuous Monitoring and Iteration**

Performance optimization is an ongoing process.

1.  **Automated Performance Testing:**
    
    *   Integrate Lighthouse or other performance tools into CI/CD pipeline to catch regressions early.
        
2.  **Regular Audits:**
    
    *   Periodically run performance audits (e.g., monthly or after major releases) to ensure performance remains optimal.
        
3.  **Monitor RUM Data:**
    
    *   Continuously monitor  RUM dashboards for any dips in performance or new bottlenecks. Set up alerts for critical performance thresholds.
        
4.  **User Feedback:**
    
    *   Encourage users to report performance issues. Their real-world experience is invaluable.
