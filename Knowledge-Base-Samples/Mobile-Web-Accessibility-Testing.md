# Mobile Web Accessibility Testing – WCAG 2.1 AA for CXS Platform
## Introduction

### Purpose
Accessibility testing on mobile devices is crucial for creating inclusive apps that everyone can use. By understanding guidelines, using built-in features, performing manual and automated testing, and involving real users, this document aims to ensure the CXS website mobile app is accessible to all.

### Scope
The scope covers all user interface components, content, and functionalities of the CXS website.

- CXS Recognize 3.0  
- CXS Develop 3.0  
- CXS Admin  

### Objectives
To ensure E2E’s digital platforms, including the website and mobile applications, are accessible to and usable by people with disabilities by identifying accessibility barriers and ensuring compliance with **WCAG 2.1 AA accessibility guidelines**.
## Accessibility Standards and Guidelines

### WCAG 2.1 AA Guidelines

This section outlines the specific **WCAG 2.1 AA** criteria that the application must comply with.  
The guidelines are organized around four core principles:

- **Perceivable** – Information and user interface components must be presented in ways that users can perceive.
- **Operable** – User interface components and navigation must be operable.
- **Understandable** – Information and the operation of the user interface must be understandable.
- **Robust** – Content must be robust enough to be interpreted reliably by a wide variety of user agents, including assistive technologies.

These four principles are commonly referred to as the **POUR principles** of accessibility.
| PRINCIPLES | ACTION PLAN | EXAMPLE |
|------------|-------------|---------|
| **Perceivable** | **Text Alternatives** – Provide text alternatives for any non-text content (e.g., images, audio). | Alt text for images. |
| | **Time-based Media** – Provide alternatives for time-based media. | Captions for videos. |
| | **Adaptable** – Create content that can be presented in different ways without losing information or structure. | Responsive design that works well on different screen sizes. |
| | **Distinguishable** – Make it easier for users to see and hear content. | Sufficient colour contrast; do not rely on colour alone to convey information. |
| **Operable** | **Keyboard Accessible** – Make all functionality available from a keyboard. | Ensure all interactive elements are keyboard accessible. |
| | **Enough Time** – Provide users enough time to read and use content. | Adjustable timing for time-limited content. |
| | **Seizures and Physical Reactions** – Do not design content in a way that is known to cause seizures or physical reactions. | Avoid flashing content. |
| | **Navigable** – Provide ways to help users navigate, find content, and determine where they are. | Consistent navigation, clear headings and labels, meaningful link text. |
| | **Input Modalities** – Make it easier for users to operate functionality through various inputs beyond keyboard. | Touch gestures should be simple and not require complex multi-finger gestures. |
| **Understandable** | **Readable** – Make text content readable and understandable. | Define abbreviations, provide pronunciation guides. |
| | **Predictable** – Make web pages appear and operate in predictable ways. | Consistent layout and behaviour; no unexpected changes of context. |
| | **Input Assistance** – Help users avoid and correct mistakes. | Error suggestions and descriptions for form fields. |
| **Robust** | **Compatible** – Maximize compatibility with current and future user agents, including assistive technologies. | Use standard HTML and ARIA to ensure compatibility. |
 
 ### Specific Considerations for Mobile

| WCAG 2.1 Guideline | Criterion | Description |
|--------------------|-----------|-------------|
| 🟦 **1.3.4** | Orientation | Ensure content is not locked to a specific orientation and works in both portrait and landscape. |
| 🟩 **1.4.10** | Reflow | Ensure content reflows to fit any screen size without requiring scrolling in two dimensions. |
| 🟨 **2.5.5** | Touch Target Size and Spacing | Ensure touch targets are large enough and have sufficient spacing to be easily activated. |
| 🟧 **2.5.4** | Motion Actuation | Ensure functionality that uses device motion can be operated through other means. |
| 🟪 **2.5.1** | Pointer Gestures | Ensure that complex gestures (like multi-touch) are not the only way to perform an action. |
| 🟥 **2.5.3** | Label in Name | Ensure the accessible name of a control includes the text that is visually presented. |

## Testing Strategy

### 🟦 Cross Device and Cross-Browser Testing
Test on different devices with varying screen sizes and resolutions to ensure responsive design and accessibility.

**💻 PC Windows**
- Chrome (Latest version and -1)
- Edge (Latest version and -1)

**🍎 macOS 10.13+**
- Safari (Latest version -1)
- Chrome (Latest version and -1)

**📱 iOS Devices** *(Latest stable release, -1, -2)*
- Safari (Latest version -1)
- Chrome (Latest version and -1)

**🤖 Android Devices** *(Latest stable release, -1, -2)*
- Chrome (Latest version and -1)
- Edge (Latest version and -1)

---

### 🟩 Automated and Manual Testing
Use automated tools to catch common accessibility issues and follow up with manual testing to address more nuanced problems.

#### ⚙️ Automated Tools
- Axe for Android/iOS
- WAVE (Web Accessibility Evaluation Tool)
- Google Accessibility Scanner (Android)
- Xcode Accessibility Inspector for iOS apps

#### 🧪 Manual Testing Tools
- Screen readers (JAWS, VoiceOver, TalkBack, ChromeVox)
- Colour contrast analysers (WebAIM Contrast Checker)
- Browser Developer Tools (built into browsers like Chrome and Safari to test web apps for accessibility issues)
- Zoom and text scaling tools

## Key Steps

This flowchart provides a structured approach to accessibility testing on mobile devices, ensuring thorough coverage and compliance with **WCAG 2.1 AA guidelines**.
<img width="889" height="557" alt="image" src="https://github.com/user-attachments/assets/e6fd7455-841a-4e79-8da4-fd6e2ed27298" />

| Category | Purpose | Benefit | Example Guideline |
|----------|---------|---------|-------------------|
| Text | • Text is rendered in adequate format, size, and colour. <br> • Text alternatives such as speech, Braille, or symbols are provided for non-text content. | • Allow users with vision impairments to read, hear, feel, or otherwise perceive content that is written in text. <br> • Allow users with cognitive disabilities to read and hear content at the same time. | Ex1. Text has a reasonable default size (14pt). <br> Ex2. Text can be resized without assistive technology up to200 %. |
| Audio | • Apps allow users to control and access audio. <br> • Apps provide alternatives to audio content, such as textual transcriptions, or captions. | • Allow users with hearing impairments to see a textual transcription and description of content that is communicated through audio. | Ex1. Audio ﬁles have text transcript. <br> Ex2. Audio is not played. automatically for more than 3 seconds; users are able to pause audio. |
| Video | • Apps provide alternatives to video content, such as captions and audio descriptions of visual content. | • Allow users with vision impairments to hear an audio transcription and description of visual content. <br> • Allow users with hearing impairment to read the audio transcript. | Ex1. Prerecorded videos have captions. <br> Ex2. Videos have extended audio description that gives the narrator adequate time to describe what is happening in the video. |
| UI Elements | • User interface elements, including images, are clearly labelled, coloured, and positioned on screen. <br> • Make it easy for users to navigate around the app, ﬁnd content, perceive it, and determine where they are in the app. | • Allow users with visual impairments to navigate the interface and locate controls and links. <br> • Allow screen reader users to access and navigate the app interface. | Ex1. UI elements (e.g. buttons, images, etc) have descriptive labels. <br> Ex2. Elements that trigger changes(buttons, links, etc) are clearly indicated. |
| User Control | • Provide users enough time to read and use content. <br> • App follows user-changed device settings. | • Users with vision impairments or cognitive disabilities who have trouble reading quickly are not restricted to perceive content by time limits. <br> • Users with mobile impairments can use the device in their preferred orientation. | Ex1. Both landscape and portrait orientation are supported. <br> Ex2. App complies with OS-level changes to settings e.g. font, and colour. |
| Flexibility and Efﬁciency | • Minimize data entry and maintain user data. <br> • Information can be accessed in multiple ways | • Users with mobile impairments or visual impairments will beneﬁt from reducing data entry related tasks. <br> • Users with visual impairments or cognitive disabilities will beneﬁt from maintained user data when the asked to re-login. | Ex1. The amount of text entry is reduced thorough the use of select menus, radio buttons, checkboxes, etc. <br> Ex2. Screen has multiple ways to reach it e.g. (search function, menu). |
| Recognition rather than Recall | • Apps must provide users with necessary information to complete task-on-hand, within the same screen. | • Users with visual impairments and cognitive disabilities can ﬁnd the information they need to complete a task without going to previous screens or looking up information | Ex1. Important information can be viewed without scrolling. <br> Ex2.Screen has title that describes the purpose. |
| Gestures | • Gestures must have alternatives, and can be replaced by other interaction options | • Users with mobile impairment can use easy to perform gestures and do not worry about activating unwanted functionalities if a wrong gesture is made. | Ex1. Gestures can be replaced by keyboard options. <br> Ex2. Touch targets close to minimum size are surrounded by inactive space. |
| System Visibility | • Application appears and operates in predictable ways that users can perceive. | • Users are not confused by system’s lack of response. <br> • Users with visual impairments will beneﬁt from knowing the system status and its response to their gesture or interaction. | Ex1. User is notiﬁed of state changes. <br> Ex2. Focus/currently selected element is clearly visible. |
| Error Prevention | • Help users avoid errors and correct mistakes when entering in-put. | • Allow users to easily and quickly ﬁnd errors in their input. <br> • Users with visual impairment, mobile impairment, and cognitive disabilities will save their time when the app ﬁnds and corrects errors. | Ex1. Identify and explain errors that can be automatically detected. Ex2.Save correct input, allow user to correct errors and proceed. |
| Tangible Interaction | • Apps have all its features accessible using tangible device e.g. physical keyboard | • Users with visual impairments or mobile impairments can use keyboards, and switches and will still be able to use the app. | Ex1. User can move focus between all elements using external keyboard <br> Ex2. All functionalities can be accessed by an external keyboard. |

## References

> WCAG 2.1 Guidelines – https://www.w3.org/TR/WCAG21/  
> Mobile Accessibility Guidelines – https://www.w3.org/WAI/standards-guidelines/mobile/  
> Study of Accessibility Guidelines of Mobile Applications – https://www.researchgate.net/publication/329494003_Study_of_Accessibility_Guidelines_of_Mobile_Applications
