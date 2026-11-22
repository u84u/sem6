# React Native Semester 7 Exam Guide

**Parul University · BCA (Honours) · Semester 7**  
**Subject focus:** React Native and Mobile Application Development  
**Source:** The five uploaded unit PDFs (`ch-1.pdf` to `ch-5.pdf`)

> This guide follows the five supplied PDFs as its sole study source. It keeps their unit order, topics, terminology, examples, and level of coverage. Explanations use straightforward English. Code appears only where it helps explain a theory point. This is a study guide, not a replacement for the original PDFs.

## How to use this guide

1. Read the unit notes from top to bottom.
2. Revise each unit's comparison tables and key points.
3. Attempt the question bank without looking at the answers.
4. Check your answers against the model answers and revise missing points.

## Exam pattern supplied by the student

| Question type | Number of questions | Marks each | Total |
|---|---:|---:|---:|
| Very short answer | 8 | 1 | 8 |
| Short answer | 4 | 2 | 8 |
| Long answer | 4 | 5 | 20 |
| **Total** | **16** |  | **36** |

Each unit contains its own practice bank in this exact structure: **8 one-mark questions, 4 two-mark questions, and 4 five-mark questions**. Every question has an exam-ready model answer.

## Contents

- [Unit 1 — Introduction to React Native Fundamentals](#unit-1--introduction-to-react-native-fundamentals)
- [Unit 2 — Adaptive User Interface Design](#unit-2--adaptive-user-interface-design)
- [Unit 3 — Navigation and State Management](#unit-3--navigation-and-state-management)
- [Unit 4 — Data Handling and API Integration](#unit-4--data-handling-and-api-integration)
- [Unit 5 — Authentication and Backend Integration](#unit-5--authentication-and-backend-integration)
- [Final revision checklist](#final-revision-checklist)

---

# Unit 1 — Introduction to React Native Fundamentals

## 1. Mobile application development

**Mobile application development** is the process of designing, creating, testing, and deploying software applications that run on mobile devices such as smartphones and tablets. The main platforms discussed in the notes are Android and iOS.

Mobile applications support many areas of everyday life:

- Communication
- Banking
- Education
- Healthcare
- Entertainment
- E-commerce
- Social media

The PDF gives WhatsApp, Instagram, Google Pay, Amazon, and YouTube as examples of mobile applications.

## 2. Types of mobile applications

### Native applications

A **native application** targets one specific mobile platform and uses that platform's programming languages.

| Platform | Languages listed in the notes |
|---|---|
| Android | Java or Kotlin |
| iOS | Swift or Objective-C |

**Advantages:** high performance, better user experience, and full access to device features.

**Disadvantages:** Android and iOS need separate codebases, development costs more, and maintenance requires more effort.

### Web applications

A **web application** runs inside a browser. The notes list HTML, CSS, and JavaScript as its core technologies.

**Advantages:** easy to develop and platform independent.

**Disadvantages:** limited access to device hardware and lower performance compared with native apps.

### Hybrid or cross-platform applications

A **cross-platform application** uses one codebase to target multiple platforms. The notes list React Native, Flutter, Ionic, and Xamarin as popular frameworks.

**Advantages:** faster development, reduced cost, and code reusability.

**Disadvantages:** performance may be slightly lower than native applications, and some platform-specific limitations may remain.

### Comparison of application types

| Type | Where it runs / how it is built | Main strengths | Main limitations |
|---|---|---|---|
| Native | Built for one platform with its platform-specific language | High performance, strong user experience, full device-feature access | Separate platform codebases, higher cost and maintenance |
| Web | Runs in a browser using HTML, CSS, and JavaScript | Easy development, platform independence | Limited hardware access, lower performance than native |
| Hybrid / cross-platform | One codebase for multiple platforms | Reuse, faster development, reduced cost | Some performance and platform-specific limitations |

### Why cross-platform development is needed

Companies use cross-platform development because it can reduce development time, simplify maintenance, allow one team to work on Android and iOS, and help applications reach the market faster. React Native is presented as one of the popular frameworks for this approach.

## 3. Introduction to React Native

**React Native** is an open-source JavaScript framework developed by Meta (Facebook) for building mobile applications. It lets developers create Android and iOS applications using JavaScript and React. The notes emphasize that React Native uses native components rather than web components, helping it provide a native mobile user experience.

### Main features

1. **Cross-platform development:** one codebase can serve Android and iOS.
2. **Component-based architecture:** applications use reusable building blocks such as buttons, headers, cards, and navigation bars.
3. **Fast Refresh:** developers can see code changes quickly without rebuilding the entire application for every change.
4. **Community support:** React Native has a developer community, libraries, and documentation.
5. **Native performance:** React Native uses native UI components, which the notes contrast with traditional hybrid applications.

### Advantages

- Reusable code
- Faster development
- Reduced cost
- Strong community support
- Easier debugging
- Large ecosystem

### Limitations

- Performance can be slightly lower than fully native applications.
- Complex native modules may require platform-specific coding.
- Dependency management can become difficult.

## 4. React Native architecture

The notes describe three main parts:

1. **JavaScript Thread:** handles business logic, API calls, and state management.
2. **Native Thread:** handles native UI rendering and device-hardware operations.
3. **Bridge:** acts as the communication layer between JavaScript and native modules.

The simplified flow shown in the PDF is:

```text
JavaScript Code  →  Bridge  →  Native Components
```

For an exam answer, define each part and state that the bridge connects the JavaScript side with native components.

### Applications named in the notes

The PDF lists Facebook, Instagram, Discord, Shopify, Walmart, and Bloomberg as examples of applications built using React Native.

## 5. Installation and environment setup

### Prerequisites

Before installing React Native, the notes list these prerequisites:

1. Node.js
2. npm or Yarn
3. Android Studio
4. JDK (Java Development Kit)

### Node.js installation check

After installing Node.js, use these commands to verify Node.js and npm:

```bash
node -v
npm -v
```

The PDF points to `https://nodejs.org` for Node.js.

### Android Studio

Android Studio supports:

- Android emulator use
- SDK management
- Device testing

Important components include the Android SDK, Android SDK Platform, and Android Virtual Device (AVD).

### React Native CLI and Expo CLI

| Feature | React Native CLI | Expo CLI |
|---|---|---|
| Full native control | Yes | Limited, as shown in the notes |
| Ease of setup | Moderate | Easy |
| Custom native modules | Supported | Limited, as shown in the notes |
| Beginner friendly | Moderate | High |

The notes present Expo as the easier starting option and React Native CLI as the option offering more native control.

### Creating an app with Expo

The PDF lists these commands:

```bash
npm install -g expo-cli
npx create-expo-app MyApp
npm start
```

### Creating an app with React Native CLI

The PDF lists:

```bash
npx react-native init MyApp
npx react-native run-android
```

## 6. React Native project structure

A typical project shown in the PDF has this structure:

```text
MyApp/
├── android/
├── ios/
├── node_modules/
├── assets/
├── components/
├── screens/
├── App.js
└── package.json
```

| File or folder | Purpose |
|---|---|
| `App.js` | Main entry point of the application |
| `components/` | Stores reusable UI components, such as `Header.js` and `Footer.js` |
| `screens/` | Stores application screens or pages, such as `HomeScreen.js` and `LoginScreen.js` |
| `assets/` | Stores images, fonts, and icons |
| `package.json` | Contains dependencies, scripts, and project configuration |
| `android/` and `ios/` | Platform-specific project folders |
| `node_modules/` | Holds installed project dependencies |

## 7. Components in React Native

A **component** is a reusable building block of a React Native application. Components help developers divide an application into smaller, understandable parts.

### Functional components

A functional component is created using a JavaScript function. The notes describe functional components as simpler, more readable, and preferred in modern React.

```jsx
import React from 'react';
import { Text } from 'react-native';

const App = () => {
  return <Text>Hello World</Text>;
};

export default App;
```

### Class components

A class component uses an ES6 class and a `render()` method to return the UI.

```jsx
import React, { Component } from 'react';
import { Text } from 'react-native';

class App extends Component {
  render() {
    return <Text>Hello World</Text>;
  }
}

export default App;
```

### Functional versus class components

| Functional component | Class component |
|---|---|
| Uses a JavaScript function | Uses an ES6 class |
| Simpler syntax | More complex structure |
| Uses Hooks in the modern approach | Uses lifecycle methods in the notes' comparison |
| Presented as the preferred modern approach | Presented as the older approach |

## 8. JSX syntax and rendering elements

**JSX** stands for **JavaScript XML**. It allows developers to write HTML-like syntax inside JavaScript. React Native uses JSX to describe the interface that a component returns.

Example:

```jsx
const element = <Text>Hello React Native</Text>;
```

### Main JSX rules

1. **Use a single parent element:** wrap sibling elements inside one parent such as `<View>`.
2. **Close every tag:** for example, write `<Image />` for a self-closing element.
3. **Use curly braces for JavaScript expressions:** for example, `<Text>{name}</Text>`.

A basic rendering example:

```jsx
import React from 'react';
import { View, Text } from 'react-native';

const App = () => {
  return (
    <View>
      <Text>Welcome to React Native</Text>
    </View>
  );
};

export default App;
```

## 9. Styling in React Native

The notes describe two styling approaches.

### Inline styling

Styles can be written directly inside the `style` prop:

```jsx
<Text style={{ color: 'blue', fontSize: 20 }}>
  Hello
</Text>
```

### StyleSheet API

The `StyleSheet` API lets developers define styles separately and reuse them.

```jsx
import { StyleSheet, Text } from 'react-native';

const styles = StyleSheet.create({
  textStyle: {
    color: 'red',
    fontSize: 22,
  },
});

<Text style={styles.textStyle}>Hello</Text>
```

**Advantages of StyleSheet API:** better readability, reusable styles, and improved performance, as stated in the PDF.

## 10. Props and state

### Props

**Props** pass data from a parent component to a child component. The notes describe props as read-only data supplied from outside the component.

```jsx
const Student = (props) => {
  return <Text>{props.name}</Text>;
};

<Student name="Rahul" />
```

### State

**State** stores dynamic data inside a component. The value can change while the application runs. The PDF gives a counter state example:

```jsx
const [count, setCount] = useState(0);
```

### Props versus state

| Props | State |
|---|---|
| Read-only from the receiving component's perspective | Mutable through the component's state update mechanism |
| Passed from a parent | Managed inside the component |
| External data | Internal component data |

## 11. Event handling and user input

Event handling lets an application respond to user actions.

### Button component

The `Button` component uses `onPress` to respond when the user presses it.

```jsx
<Button
  title="Click Me"
  onPress={() => alert('Button Pressed')}
/>
```

### TextInput component

`TextInput` accepts text entered by the user. The notes show a placeholder example:

```jsx
<TextInput placeholder="Enter Name" />
```

### Touchable components

The notes list:

- `TouchableOpacity`
- `TouchableHighlight`
- `TouchableWithoutFeedback`

Example:

```jsx
<TouchableOpacity onPress={() => alert('Pressed')}>
  <Text>Press Here</Text>
</TouchableOpacity>
```

The PDF also demonstrates connecting a `TextInput` to state through `value` and `onChangeText`, then showing the entered name when the user presses a button. This demonstrates that input, state, and events work together.

## 12. Debugging tools and common errors

**Debugging** helps developers find errors, improve performance, and fix crashes.

### Tools listed in the PDF

1. **`console.log()`** — prints a message or value for inspection.
2. **React Developer Tools** — helps inspect component hierarchy, state, and props.
3. **Emulator testing** — checks the application with an Android Emulator or a physical device.

### Common errors

| Error | Reason given in the notes |
|---|---|
| Module not found | Missing dependency |
| Undefined is not a function | Incorrect method usage |
| Metro bundler issue | Cache problem |

### Best practices

- Use reusable components.
- Keep code modular.
- Use functional components.
- Avoid unnecessary re-rendering.
- Maintain a proper folder structure.
- Write clean and readable code.
- Use version control systems such as Git.

## Unit 1 — Quick revision

- Mobile applications target devices such as smartphones and tablets.
- Native apps target one platform; web apps run in browsers; cross-platform apps share a codebase.
- React Native is an open-source JavaScript framework developed by Meta.
- The architecture topics are JavaScript Thread, Native Thread, and Bridge.
- Environment setup includes Node.js, npm/Yarn, Android Studio, and JDK.
- `App.js` is the main entry point in the shown project structure.
- Components are reusable building blocks; JSX describes UI.
- Props pass data into components; state stores changing internal data.
- `onPress` handles button presses; `TextInput` accepts text.
- Debugging tools include `console.log()`, React Developer Tools, and emulator testing.

## Unit 1 — Question bank with model answers

### A. One-mark questions (8 × 1)

**1. What is mobile application development?**  
It is the process of designing, creating, testing, and deploying software applications for mobile devices such as smartphones and tablets.

**2. Name the two mobile platforms discussed in the unit.**  
Android and iOS.

**3. What is React Native?**  
React Native is an open-source JavaScript framework developed by Meta for building mobile applications.

**4. What does JSX stand for?**  
JSX stands for JavaScript XML.

**5. What is a component in React Native?**  
A component is a reusable building block of a React Native application.

**6. What is the main purpose of `App.js`?**  
It acts as the main entry point of the application in the project structure shown in the notes.

**7. What are props?**  
Props are used to pass data from a parent component to a child component.

**8. Name one debugging tool used in React Native.**  
`console.log()`. (React Developer Tools and emulator testing are also valid.)

### B. Two-mark questions (4 × 2)

**1. State two advantages of native applications.**  
Native applications provide high performance and a better user experience. They also offer full access to device features.

**2. Write two features of React Native.**  
React Native supports cross-platform development through a shared codebase. It also uses reusable components and provides Fast Refresh.

**3. Differentiate between props and state.**  
Props pass data from a parent component and are read-only to the receiving component. State stores dynamic data inside a component and can change during application execution.

**4. Name any two prerequisites for React Native setup and state their purpose.**  
Node.js provides the JavaScript runtime, while Android Studio provides tools such as the Android emulator and SDK management. npm/Yarn and JDK are also listed prerequisites.

### C. Five-mark questions (4 × 5)

**1. Explain the types of mobile applications with their advantages and disadvantages.**  
Mobile applications are commonly grouped into three types:

- **Native applications:** built for one platform using its specific language, such as Java/Kotlin for Android and Swift/Objective-C for iOS. They offer high performance, a better user experience, and full device-feature access. They need separate codebases, cost more, and require more maintenance.
- **Web applications:** run in a browser using HTML, CSS, and JavaScript. They are easy to develop and platform independent, but have limited hardware access and lower performance than native applications.
- **Hybrid/cross-platform applications:** use one codebase for multiple platforms. Frameworks named in the notes include React Native, Flutter, Ionic, and Xamarin. They reduce development time and cost and support code reuse, but may have slightly lower performance and some platform-specific limitations.

**2. Define React Native and explain its features, advantages, and limitations.**  
React Native is an open-source JavaScript framework developed by Meta for creating Android and iOS applications using JavaScript and React. Its important features are cross-platform development, component-based architecture, Fast Refresh, community support, and native UI components. Its advantages include reusable code, faster development, reduced cost, easier debugging, and a large ecosystem. Its limitations include slightly lower performance than native apps, platform-specific coding for complex native modules, and difficult dependency management.

**3. Explain the architecture of React Native.**  
The unit describes three main parts:

1. **JavaScript Thread:** handles business logic, API calls, and state management.
2. **Native Thread:** handles native UI rendering and device-hardware operations.
3. **Bridge:** provides communication between JavaScript and native modules.

The simplified flow is `JavaScript Code → Bridge → Native Components`. Thus, the JavaScript side communicates with native components through the bridge.

**4. Explain the React Native project structure and the purpose of its important files and folders.**  
A typical project includes `android/`, `ios/`, `node_modules/`, `assets/`, `components/`, `screens/`, `App.js`, and `package.json`. `App.js` is the main entry point. `components/` stores reusable UI parts such as headers and footers. `screens/` stores pages such as Home and Login. `assets/` stores images, fonts, and icons. `package.json` stores dependencies, scripts, and project configuration. The Android and iOS folders contain platform project files, while `node_modules/` contains installed dependencies.

---

# Unit 2 — Adaptive User Interface Design

## 1. Introduction to mobile UI/UX design

### UI design

**UI (User Interface) design** concerns the visual appearance and interactive elements of a mobile application. The PDF lists buttons, menus, icons, layouts, colors, and typography. Its main objective is to make the application visually attractive and easy to interact with.

### UX design

**UX (User Experience) design** focuses on the user's overall experience while interacting with an application. It emphasizes ease of use, accessibility, performance, simple navigation, and user satisfaction. Good UX helps users complete tasks efficiently without confusion.

### Importance of UI/UX

Good UI/UX can improve engagement, satisfaction, accessibility, usability, and application popularity while reducing frustration. Poor UI/UX can cause confusion, uninstalls, negative reviews, and lower user retention.

## 2. Principles of effective mobile UI/UX design

1. **Simplicity:** keep the interface clean and understandable. Use clear buttons, minimal text, and an organized layout.
2. **Consistency:** maintain consistent colors, fonts, buttons, and navigation styles. Consistency helps users become familiar with the application.
3. **Responsiveness:** adapt the interface to different screen sizes, devices, and orientation changes.
4. **Accessibility:** make the application usable for people with disabilities. The notes mention screen readers, voice feedback, and proper text contrast.
5. **User feedback:** show users that an action has happened or is being processed. Examples include loading indicators, error messages, and success notifications.

## 3. Responsive layouts using Flexbox

**Flexbox** is a layout system used to arrange UI elements dynamically and responsively. React Native uses Flexbox by default. It helps align components, distribute space, and build layouts for different screen sizes.

### Important Flexbox properties

| Property | Purpose | Values or example in the notes |
|---|---|---|
| `flexDirection` | Sets the direction of child components | `row`, `column` |
| `justifyContent` | Aligns children along the main axis | `flex-start`, `center`, `flex-end`, `space-between`, `space-around` |
| `alignItems` | Aligns children along the cross axis | `flex-start`, `center`, `flex-end`, `stretch` |
| `flex` | Determines how much space a component occupies | Example: `flex: 1` |

Example of a row layout:

```jsx
<View style={{ flexDirection: 'row' }}>
  <Text>Item 1</Text>
  <Text>Item 2</Text>
</View>
```

A responsive layout in the PDF places two child views inside a parent with `flex: 1` and `flexDirection: 'row'`. Each child uses `flex: 1`, so the two boxes share the available horizontal space.

**Advantages of Flexbox:** easy responsive design, dynamic layouts, better alignment control, and support across multiple screen sizes.

## 4. Working with the Dimensions API

The **Dimensions API** gets the screen width and screen height. Developers can use these dimensions to create layouts that adapt to different devices.

```jsx
import { Dimensions } from 'react-native';

const width = Dimensions.get('window').width;
const height = Dimensions.get('window').height;
```

The PDF demonstrates displaying the screen width using a `Text` component. The stated importance of the API is that it supports dynamic layouts, improves responsiveness, and accommodates multiple device sizes.

## 5. Platform-specific design

React Native applications can run on Android and iOS, but some interface conventions differ.

### Android versus iOS as shown in the notes

| Feature | Android | iOS |
|---|---|---|
| Navigation style | Material Design | Cupertino Design |
| Buttons | Elevated buttons | Flat buttons |
| Fonts | Roboto | San Francisco |
| Back navigation | Hardware button | Gesture-based |

### Platform API

React Native provides the `Platform` API. The PDF shows `Platform.OS` to check the current operating system:

```jsx
import { Platform } from 'react-native';

if (Platform.OS === 'android') {
  console.log('Android Device');
}
```

### Platform-specific files

Developers can create separate files such as `Home.android.js` and `Home.ios.js`. This allows them to implement platform-specific code. The notes list better user experience, native-like feel, and improved usability as advantages.

## 6. Media queries and screen-orientation handling

The notes explain that mobile devices commonly support **portrait** and **landscape** modes. Applications should adapt to both orientations.

The PDF shows an orientation/dimension-change listener using the Dimensions API:

```jsx
Dimensions.addEventListener('change', ({ window }) => {
  console.log(window.width);
});
```

The responsive techniques named in the notes are Flexbox, percentage-based sizing, and dynamic dimensions. Handling orientation can improve readability, usability, and responsiveness.

## 7. Theming and dark mode

### Theming

**Theming** allows an application to maintain a consistent set of colors, fonts, and UI styles.

### Dark mode

**Dark mode** changes the application appearance to darker colors. The PDF lists reduced eye strain, battery saving on OLED screens, and better night-time usability as benefits.

### Appearance API

React Native provides the Appearance API. The notes show how to read the current color scheme:

```jsx
import { Appearance } from 'react-native';

const colorScheme = Appearance.getColorScheme();
const isDarkMode = colorScheme === 'dark';
```

Dark mode can improve visual comfort, provide a modern appearance, and support user preferences.

## 8. Custom fonts and icons

### Custom fonts

Custom fonts improve an application's appearance and branding. The PDF lists these steps:

1. Create an `assets/fonts` folder.
2. Add the font files.
3. Configure `react-native.config.js`.
4. Link the assets.

A font can then be selected using the `fontFamily` style property:

```jsx
<Text style={{ fontFamily: 'Roboto' }}>
  Welcome
</Text>
```

### Icons

Icons improve UI clarity and navigation. The notes name `react-native-vector-icons` as a popular library.

```bash
npm install react-native-vector-icons
```

Example usage:

```jsx
import Icon from 'react-native-vector-icons/FontAwesome';

<Icon name="home" size={30} color="blue" />
```

Custom fonts and icons can improve visual appeal, interaction, and professional design.

## 9. Accessibility features

**Accessibility** means designing applications so people with disabilities can use them.

The PDF lists these React Native features:

- **`accessibilityLabel`:** provides a description for screen readers. The example labels a button as “Login Button”.
- **`accessible`:** marks an element as accessible, for example `<View accessible={true}>`.
- **Screen readers:** TalkBack is listed for Android and VoiceOver for iOS.

Accessibility supports inclusive applications, better usability, legal compliance, and user satisfaction.

## 10. Best practices for user-friendly interface design

The PDF recommends:

1. Maintain consistent colors, fonts, and button styles.
2. Keep navigation simple so users can move easily between screens.
3. Use proper spacing and avoid overcrowded layouts.
4. Optimize performance and avoid heavy UI rendering.
5. Use readable fonts on different screen sizes.
6. Provide feedback with alerts, loading indicators, and success messages.
7. Design for small screens, large screens, and tablets.
8. Improve accessibility through screen readers, voice commands, and proper color contrast.
9. Test the UI on real devices to find layout, responsiveness, and performance issues.

### Practical example: responsive login screen

The PDF's example uses a parent `View` with `flex: 1`, centered content, and padding. It contains email and password `TextInput` elements and a Login button. The password field uses `secureTextEntry={true}`. The example demonstrates how layout styles and input components combine to form a simple login UI.

## Unit 2 — Quick revision

- UI concerns visual appearance and interactive elements; UX concerns the overall user experience.
- The five principles are simplicity, consistency, responsiveness, accessibility, and user feedback.
- Flexbox uses `flexDirection`, `justifyContent`, `alignItems`, and `flex` to arrange views.
- The Dimensions API reads window width and height.
- The Platform API and `.android.js` / `.ios.js` files support platform-specific design.
- Mobile orientation includes portrait and landscape.
- The Appearance API reads the color scheme for theming and dark mode.
- Custom fonts and icons support visual identity and clarity.
- `accessibilityLabel`, `accessible`, TalkBack, and VoiceOver support accessibility.
- Test layouts on real devices and design for different screen sizes.

## Unit 2 — Question bank with model answers

### A. One-mark questions (8 × 1)

**1. What is UI design?**  
UI design concerns the visual appearance and interactive elements of a mobile application.

**2. What is UX design?**  
UX design focuses on the overall experience of users while they interact with an application.

**3. What is Flexbox?**  
Flexbox is a layout system used to arrange UI elements dynamically and responsively.

**4. Name the two values of `flexDirection` given in the notes.**  
`row` and `column`.

**5. What does the Dimensions API provide?**  
It provides screen width and screen height.

**6. Name the React Native API used to detect the operating system.**  
The Platform API.

**7. What does dark mode do?**  
It changes the application's appearance to darker colors.

**8. Name the Android and iOS screen readers listed in the PDF.**  
TalkBack for Android and VoiceOver for iOS.

### B. Two-mark questions (4 × 2)

**1. Differentiate between UI and UX design.**  
UI design focuses on visual elements such as buttons, menus, icons, layouts, colors, and typography. UX design focuses on ease of use, accessibility, performance, navigation simplicity, and user satisfaction.

**2. Explain `justifyContent` and `alignItems`.**  
`justifyContent` controls alignment along the main axis. `alignItems` controls alignment along the cross axis.

**3. State two benefits of responsive design.**  
Responsive design allows an application to adapt to different screen sizes and devices. It also supports orientation changes and improves usability.

**4. What is the purpose of `accessibilityLabel`?**  
`accessibilityLabel` provides a description of an interface element for screen readers. For example, a button can have the label “Login Button”.

### C. Five-mark questions (4 × 5)

**1. Explain the principles of effective mobile UI/UX design.**  
The PDF lists five principles:

1. **Simplicity:** use a clean interface, clear buttons, minimal text, and an organized layout.
2. **Consistency:** keep colors, fonts, buttons, and navigation styles consistent.
3. **Responsiveness:** adapt the interface to different devices, screen sizes, and orientations.
4. **Accessibility:** support users with disabilities through screen readers, voice feedback, and proper text contrast.
5. **User feedback:** provide loading indicators, error messages, and success notifications so users understand the result of an action.

**2. Explain the important Flexbox properties used in React Native.**  
Flexbox arranges UI elements dynamically, and React Native uses it by default. `flexDirection` sets the child direction using `row` or `column`. `justifyContent` aligns children along the main axis with values such as `flex-start`, `center`, `flex-end`, `space-between`, and `space-around`. `alignItems` aligns children on the cross axis with values such as `flex-start`, `center`, `flex-end`, and `stretch`. `flex` determines how much space a component occupies. These properties help create responsive layouts.

**3. Explain how React Native supports platform-specific design and screen orientation.**  
Android and iOS use different interface conventions. The notes compare Material Design with Cupertino Design, elevated buttons with flat buttons, Roboto with San Francisco, and hardware back navigation with gesture-based navigation. The Platform API can identify the operating system through `Platform.OS`. Developers can also create files such as `Home.android.js` and `Home.ios.js`. For orientation, the notes identify portrait and landscape modes and show listening for dimension changes through the Dimensions API. Flexbox, percentage sizing, and dynamic dimensions help layouts adapt.

**4. Explain theming, dark mode, and accessibility features in React Native.**  
Theming maintains consistent colors, fonts, and UI styles. Dark mode changes the interface to darker colors and the PDF lists reduced eye strain, OLED battery saving, and better night-time usability as benefits. The Appearance API reads the current color scheme. Accessibility ensures that users with disabilities can use the application. React Native features listed include `accessibilityLabel` for screen-reader descriptions and `accessible` for marking an element accessible. The PDF names TalkBack on Android and VoiceOver on iOS as screen readers.

---

# Unit 3 — Navigation and State Management

## 1. Navigation in mobile applications

**Navigation** is the process of moving between screens or pages in a mobile application. Examples include moving from Login to Home, opening Profile from a menu, and switching between Home, Search, and Settings tabs.

Good navigation provides easy access to features, better user experience, organized structure, faster interaction, and improved usability. Poor navigation can confuse users and reduce usability.

The unit introduces three common types: stack navigation, tab navigation, and drawer navigation.

## 2. React Navigation library

**React Navigation** is a popular library used to implement navigation in React Native applications. It provides screen transitions, navigation containers, navigation stacks, tab navigation, and drawer navigation.

The PDF lists these features:

- Easy to use
- Cross-platform support
- Multiple navigation types
- High customization
- Strong community support

### Installation steps shown in the notes

```bash
npm install @react-navigation/native
npm install react-native-screens react-native-safe-area-context
npm install @react-navigation/native-stack
```

### NavigationContainer

`NavigationContainer` manages the navigation structure of the application. The navigators are placed inside it.

## 3. Stack navigation

**Stack navigation** works like a stack data structure. New screens are pushed onto the stack, and previous screens are popped from it.

Common uses in the notes include login flows, product details, and multi-step forms.

The PDF shows this installation command:

```bash
npm install @react-navigation/native-stack
```

A basic stack contains a `Stack.Navigator` and named `Stack.Screen` entries. A screen can move to another screen through `navigation.navigate('Profile')`.

```jsx
const Stack = createNativeStackNavigator();

function HomeScreen({ navigation }) {
  return (
    <Button
      title="Go to Profile"
      onPress={() => navigation.navigate('Profile')}
    />
  );
}

<NavigationContainer>
  <Stack.Navigator>
    <Stack.Screen name="Home" component={HomeScreen} />
    <Stack.Screen name="Profile" component={ProfileScreen} />
  </Stack.Navigator>
</NavigationContainer>
```

**Advantages:** simple implementation, smooth transitions, and suitability for sequential workflows.

**Limitations:** can become difficult in complex applications and is not suitable for top-level navigation in the notes' comparison.

## 4. Tab navigation

**Tab navigation** lets users switch between screens using tabs at the top or bottom of the screen. The PDF names Instagram, WhatsApp, and Facebook as examples.

Types:

1. **Bottom Tab Navigation:** tabs appear at the bottom.
2. **Material Top Tabs:** tabs appear at the top.

The notes show this installation command:

```bash
npm install @react-navigation/bottom-tabs
```

A bottom tab navigator uses `createBottomTabNavigator()`, a `Tab.Navigator`, and named `Tab.Screen` entries. The PDF lists easy screen switching, better accessibility, and a user-friendly interface as advantages.

## 5. Drawer navigation

**Drawer navigation** displays a side menu that slides from the left or right side of the screen. The notes mention e-commerce applications, dashboard applications, and banking applications as common uses.

Installation command:

```bash
npm install @react-navigation/drawer
```

A drawer navigator uses `createDrawerNavigator()`, a `Drawer.Navigator`, and named `Drawer.Screen` entries. The PDF lists saving screen space, organizing multiple screens, and easy access to features as advantages.

## 6. Stack, tab, and drawer navigation compared

| Navigation type | How it works | Common use / strength |
|---|---|---|
| Stack | Pushes new screens and pops previous screens | Login flows, product details, and multi-step forms |
| Tab | Switches screens through top or bottom tabs | Frequent switching between main sections |
| Drawer | Opens a side menu from the left or right | Menus for applications with several sections |

## 7. Navigation lifecycle and screen management

The notes explain three general screen lifecycle stages:

1. **Mounting:** the screen is created.
2. **Updating:** the screen changes as its data or state changes.
3. **Unmounting:** the screen is removed.

React Navigation events named in the PDF are:

- `focus`
- `blur`
- `beforeRemove`

Example listener:

```jsx
navigation.addListener('focus', () => {
  console.log('Screen Focused');
});
```

Good screen management can reduce memory usage, improve performance, and avoid unnecessary rendering.

## 8. Passing parameters between screens

Parameters transfer data from one screen to another. The PDF gives product IDs, usernames, and user profile details as examples.

### Passing a parameter

```jsx
navigation.navigate('Profile', {
  username: 'Rahul',
});
```

### Receiving a parameter

```jsx
function ProfileScreen({ route }) {
  const { username } = route.params;
  return <Text>{username}</Text>;
}
```

The stated benefits are dynamic data transfer, better interaction, and reusable screens.

## 9. Nested navigation structures

**Nested navigation** means combining multiple navigation types. Examples in the notes include a drawer containing tab navigation and a stack inside tab navigation.

Example structure:

```text
Drawer Navigation
├── Home Tabs
│   ├── Feed Screen
│   └── Profile Screen
└── Settings Screen
```

Nested navigation supports better organization, scalable architecture, and large applications.

## 10. Introduction to state management

**State** is data that changes during application execution. The PDF gives login status, cart items, counter value, and theme mode as examples.

State management helps share data between components, update the UI dynamically, and maintain application consistency.

### Local state

Local state is managed inside one component. The PDF gives this example:

```jsx
const [count, setCount] = useState(0);
```

### Global state

Global state is shared across multiple components. Examples in the notes include user authentication, shopping cart, and application theme.

## 11. Context API for global state management

**Context API** is React's built-in state management solution for sharing data globally. It helps avoid **prop drilling**, which means repeatedly passing data through components that do not need to use it directly.

The basic steps are:

1. Create a context using `createContext()`.
2. Provide a value through `Context.Provider`.
3. Read the value in a child component using `useContext()`.

```jsx
import React, { createContext, useContext } from 'react';
import { Text } from 'react-native';

const UserContext = createContext();

function Profile() {
  const user = useContext(UserContext);
  return <Text>{user}</Text>;
}

function App() {
  return (
    <UserContext.Provider value="Rahul">
      <Profile />
    </UserContext.Provider>
  );
}
```

**Advantages:** simple global state management, less prop drilling, and built-in availability in React.

**Limitations:** not suitable for very large applications according to the notes, and frequent updates may reduce performance.

## 12. Handling complex state

Complex state becomes difficult when an application contains multiple screens, large datasets, or real-time updates.

The PDF lists these common solutions:

- Context API
- Redux
- Zustand
- Recoil

## 13. Performance optimization and avoiding unnecessary re-renders

**Re-rendering** means updating the UI again when state or props change. Too many re-renders can reduce performance, increase memory usage, and slow down applications.

The notes list these techniques:

- **`React.memo()`:** helps prevent unnecessary rendering of a component.
- **`useMemo()`:** optimizes expensive calculations.
- **`useCallback()`:** optimizes functions.
- **Lazy loading:** loads components only when needed.
- **FlatList optimization:** use `FlatList` instead of `ScrollView` for large data.

Example from the PDF:

```jsx
export default React.memo(MyComponent);

const result = useMemo(() => {
  return calculateValue();
}, []);

const handleClick = useCallback(() => {
  console.log('Clicked');
}, []);
```

The PDF also shows `FlatList` with `data` and `renderItem` properties.

## Unit 3 — Quick revision

- Navigation moves users between screens.
- React Navigation supports stack, tab, and drawer navigation.
- `NavigationContainer` manages the navigation structure.
- Stack navigation pushes and pops screens.
- Tab navigation switches through top or bottom tabs.
- Drawer navigation opens a sliding side menu.
- Lifecycle stages are mounting, updating, and unmounting.
- Navigation events include `focus`, `blur`, and `beforeRemove`.
- Screens exchange values through route parameters.
- Nested navigation combines multiple navigator types.
- Local state belongs to one component; global state is shared.
- Context API uses `createContext`, `Provider`, and `useContext`.
- `React.memo`, `useMemo`, `useCallback`, lazy loading, and FlatList optimization help performance.

## Unit 3 — Question bank with model answers

### A. One-mark questions (8 × 1)

**1. What is navigation in a mobile application?**  
Navigation is the process of moving between different screens or pages within a mobile application.

**2. Name the library commonly used for navigation in React Native.**  
React Navigation.

**3. What is stack navigation?**  
Stack navigation is a navigation method in which new screens are pushed onto a stack and previous screens are popped.

**4. Where can tabs appear in tab navigation?**  
Tabs can appear at the bottom or at the top of the screen.

**5. What is drawer navigation?**  
Drawer navigation displays a side menu that slides from the left or right side of the screen.

**6. Name one navigation lifecycle event.**  
`focus`. (`blur` and `beforeRemove` are also valid.)

**7. What is local state?**  
Local state is state managed inside a single component.

**8. What is the purpose of Context API?**  
Context API shares data globally across components and helps avoid prop drilling.

### B. Two-mark questions (4 × 2)

**1. State two advantages of React Navigation.**  
It supports multiple navigation styles and cross-platform applications. It is also customizable and provides screen transitions.

**2. Differentiate between tab navigation and drawer navigation.**  
Tab navigation lets users switch between screens using tabs at the top or bottom. Drawer navigation opens a sliding side menu from the left or right.

**3. What is nested navigation? Give one example.**  
Nested navigation combines multiple navigation types in one application. One example is a drawer containing tab navigation.

**4. State two limitations of Context API from the notes.**  
The notes say Context API is not suitable for very large applications and frequent updates may reduce performance.

### C. Five-mark questions (4 × 5)

**1. Explain stack, tab, and drawer navigation.**  
React Native uses React Navigation to implement different navigation styles:

- **Stack navigation:** works like a stack data structure. New screens are pushed onto the stack and previous screens are popped. It suits login flows, product details, and multi-step forms.
- **Tab navigation:** allows users to switch between screens using tabs at the bottom or top. Types named in the notes are Bottom Tab Navigation and Material Top Tabs.
- **Drawer navigation:** displays a side menu that slides from the left or right. It is used in e-commerce, dashboards, and banking applications.

Stack navigation supports sequential workflows, tab navigation provides quick switching, and drawer navigation organizes multiple sections.

**2. Explain the navigation lifecycle and passing parameters between screens.**  
The screen lifecycle contains mounting, updating, and unmounting. React Navigation provides events such as `focus`, `blur`, and `beforeRemove`. A screen can register a listener for a focus event. Parameters transfer data between screens. For example, `navigation.navigate('Profile', { username: 'Rahul' })` sends a username to the Profile screen. The receiving screen reads it through `route.params`. Parameter passing supports dynamic data transfer, user interaction, and reusable screens.

**3. Explain state management and Context API.**  
State is data that changes during application execution. Local state is managed inside one component, while global state is shared across multiple components. State management helps share information, update the UI dynamically, and maintain consistency. Context API is React's built-in solution for sharing data globally. Developers create a context with `createContext()`, provide a value through `Context.Provider`, and read it with `useContext()`. It reduces prop drilling and offers simple global state management. Its limitations in the notes are difficulty with very large applications and possible performance reduction with frequent updates.

**4. Explain techniques for avoiding unnecessary re-renders and optimizing performance.**  
Re-rendering updates the UI when state or props change. Too many re-renders can reduce performance, increase memory use, and slow an application. The notes list `React.memo()` to prevent unnecessary component rendering, `useMemo()` to optimize expensive calculations, and `useCallback()` to optimize functions. Lazy loading loads components only when needed. For large datasets, the notes recommend `FlatList` instead of `ScrollView`. These techniques help improve application performance.

---

# Unit 4 — Data Handling and API Integration

## 1. Introduction to data handling

**Data handling** is the process of collecting data from users, processing it, validating information, sending data to servers, and receiving and displaying data.

Mobile applications interact with user inputs, APIs, databases, and local storage systems. Examples include login forms, registration forms, search systems, product listings, and chat applications.

### Importance of data handling

Proper data handling improves application reliability, reduces errors, enhances user experience, protects sensitive information, and improves performance. Poor handling can cause invalid input, crashes, security vulnerabilities, and poor user experience.

## 2. Handling and optimizing user inputs

**User input** is information entered by a user into an application. The notes list these common input components:

- `TextInput`
- `Button`
- `Switch`
- `Picker`
- `Checkbox`

### TextInput component

`TextInput` accepts text from a user. The PDF demonstrates connecting the field to state through `value` and `onChangeText`:

```jsx
const [name, setName] = useState('');

<TextInput
  placeholder="Enter Name"
  value={name}
  onChangeText={setName}
/>
```

### Input optimization techniques

Input optimization improves responsiveness, user experience, and data quality. The notes list:

1. **Input validation:** check that users enter correct data, such as a valid email format or an adequately long password.
2. **Limiting input length:** use `maxLength`, for example `maxLength={10}`.
3. **Keyboard types:** choose a suitable keyboard for the field, such as `email-address` for email input.

The PDF lists these keyboard types:

| Keyboard type | Usage |
|---|---|
| `default` | General text |
| `numeric` | Numbers |
| `email-address` | Email addresses |
| `phone-pad` | Phone numbers |

## 3. Controlled and uncontrolled components

### Controlled component

A **controlled component** has its input value controlled by React state. The example uses `value` and `onChangeText` together.

```jsx
const [email, setEmail] = useState('');

<TextInput
  value={email}
  onChangeText={setEmail}
/>
```

Advantages listed in the PDF are better validation, easier data handling, and real-time updates.

### Uncontrolled component

An **uncontrolled component** handles the input value directly without state management. The PDF gives `defaultValue` as an example:

```jsx
<TextInput defaultValue="Hello" />
```

### Comparison

| Controlled | Uncontrolled |
|---|---|
| Uses state | Does not use state management for the value |
| Better validation | Simpler implementation |
| Supports dynamic updates | Offers more limited control |

## 4. Form handling techniques

**Form handling** means managing forms that collect user input, such as login forms, registration forms, and feedback forms.

A basic form in the notes uses state for username and password, `TextInput` for each field, and a Button to submit the form. The password field uses `secureTextEntry={true}`. The button's `onPress` handler calls a submission function.

### Form handling libraries

The PDF names:

- Formik
- React Hook Form

The notes list simplified validation, better performance, and reduced code complexity as advantages of form libraries.

## 5. Form validation

**Form validation** checks whether user input is correct, complete, and properly formatted.

### Types of validation

1. **Client-side validation:** takes place before the application sends data to the server.
2. **Server-side validation:** takes place on the server after the application submits data.

### Examples from the PDF

Manual check for an empty email:

```jsx
if (email === '') {
  alert('Email Required');
}
```

The PDF also shows an email regular expression:

```jsx
const emailRegex = /^[^ ]+@[^ ]+\.[a-z]{2,3}$/;
```

The password rules listed are minimum length, uppercase letters, numbers, and special characters.

**Benefits:** validation prevents invalid data, improves security, and enhances user experience.

## 6. Introduction to REST APIs

**API** stands for **Application Programming Interface**. It allows communication between mobile applications, web servers, and databases.

**REST** stands for **Representational State Transfer**. A REST API is a web service architecture used for communication over HTTP. The notes identify mobile applications, web applications, and cloud systems as common uses.

### HTTP methods

| Method | Purpose in the notes |
|---|---|
| GET | Retrieve data |
| POST | Create data |
| PUT | Update data |
| DELETE | Remove data |

Example URL from the PDF:

`https://jsonplaceholder.typicode.com/posts`

The notes list lightweight communication, fast communication, platform independence, and easy integration as REST API benefits.

## 7. Making HTTP requests using the Fetch API

The **Fetch API** communicates with servers and retrieves data. The notes describe it as built into JavaScript, easy to use, and based on promises.

### GET request

```jsx
fetch('https://jsonplaceholder.typicode.com/posts')
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.log(error));
```

The response is converted to JSON, then the resulting data is handled. The catch handler handles an error.

### POST request

The PDF demonstrates a POST request with a method, JSON content-type header, and JSON-encoded body:

```jsx
fetch('https://jsonplaceholder.typicode.com/posts', {
  method: 'POST',
  headers: {
    'Content-Type': 'application/json',
  },
  body: JSON.stringify({
    title: 'React Native',
  }),
});
```

**Advantages:** built into JavaScript, easy to use, and supports promises.

**Limitations in the notes:** complex error handling and no automatic request cancellation.

## 8. Axios library

**Axios** is an HTTP client library used for API communication.

Installation:

```bash
npm install axios
```

GET request example:

```jsx
import axios from 'axios';

axios.get('https://jsonplaceholder.typicode.com/posts')
  .then(response => {
    console.log(response.data);
  })
  .catch(error => {
    console.log(error);
  });
```

POST request example:

```jsx
axios.post('https://jsonplaceholder.typicode.com/posts', {
  title: 'Mobile App',
});
```

The PDF lists better error handling, cleaner syntax, request cancellation support, and automatic JSON conversion as Axios advantages.

### Fetch API versus Axios

| Fetch API | Axios |
|---|---|
| Built into JavaScript | External library |
| Requires manual JSON parsing in the notes' comparison | Automatic JSON parsing in the notes' comparison |
| Error handling is described as more complex | Error handling is described as simpler |

## 9. Handling API responses and errors

Applications should display retrieved data, manage loading states, and handle errors properly.

### Common errors

| Error | Cause listed in the notes |
|---|---|
| 404 | Resource not found |
| 500 | Server error |
| Network error | Internet issue |
| Timeout | Slow server response |

### Error-handling best practices

1. Show meaningful error messages.
2. Use loading indicators.
3. Retry failed requests.
4. Validate server responses.

The PDF shows a loading state such as:

```jsx
const [loading, setLoading] = useState(true);
```

## 10. Loading indicators and user feedback

Loading indicators tell users that the application is processing a request. Without them, users may think the application has frozen.

The notes show React Native's `ActivityIndicator`:

```jsx
import { ActivityIndicator } from 'react-native';

<ActivityIndicator size="large" />
```

Other user-feedback mechanisms listed are alerts, toast messages, success notifications, and error dialogs. The PDF gives this alert example:

```jsx
alert('Data Saved Successfully');
```

User feedback improves interaction, usability, and communication.

## 11. Local storage using AsyncStorage

**AsyncStorage** is a local storage system used to store data persistently inside a mobile application. The PDF gives login tokens, user preferences, and offline data as examples.

Installation:

```bash
npm install @react-native-async-storage/async-storage
```

The notes show three main operations:

```jsx
import AsyncStorage from '@react-native-async-storage/async-storage';

// Store
await AsyncStorage.setItem('username', 'Rahul');

// Retrieve
const value = await AsyncStorage.getItem('username');

// Remove
await AsyncStorage.removeItem('username');
```

**Advantages:** persistent storage, offline support, and simple implementation.

**Limitations:** not suitable for large databases and limited security.

## 12. Data caching and offline handling

**Data caching** stores frequently used data temporarily to improve performance.

Benefits include faster loading, reduced internet usage, and a better offline experience.

Applications should continue to work when there is no internet connection. The notes give offline notes applications and cached news articles as examples.

### Offline strategy

1. Store data locally.
2. Synchronize data when the internet connection returns.
3. Show cached data while offline.

The PDF's example workflow is:

```text
API Request
    ↓
Store Data in AsyncStorage
    ↓
Retrieve Cached Data Offline
```

## Unit 4 — Quick revision

- Data handling covers collection, processing, validation, sending, receiving, and displaying data.
- `TextInput` accepts user input; `value` and `onChangeText` connect a controlled field to state.
- `maxLength` limits input length; `keyboardType` selects an appropriate keyboard.
- Controlled components use state; uncontrolled components do not use state to control the value.
- Form validation can be client-side or server-side.
- REST uses HTTP; GET retrieves, POST creates, PUT updates, and DELETE removes data.
- Fetch is built in; Axios is an external HTTP client library.
- Applications should handle loading, errors, and user feedback.
- AsyncStorage stores persistent local data through set, get, and remove operations.
- Caching improves load time and supports offline access.

## Unit 4 — Question bank with model answers

### A. One-mark questions (8 × 1)

**1. What is data handling?**  
Data handling is the process of collecting, processing, validating, sending, receiving, and displaying data.

**2. What is the purpose of the TextInput component?**  
It accepts text input from users.

**3. What is a controlled component?**  
A controlled component is an input component whose value React state controls.

**4. What does API stand for?**  
Application Programming Interface.

**5. What does REST stand for?**  
Representational State Transfer.

**6. Which HTTP method retrieves data?**  
GET.

**7. What is Axios?**  
Axios is a popular HTTP client library used for API communication.

**8. What is AsyncStorage?**  
AsyncStorage is a local storage system used to store data persistently inside mobile applications.

### B. Two-mark questions (4 × 2)

**1. State two ways to optimize user input.**  
Validate input to check correctness and use `maxLength` to limit the number of characters. Suitable keyboard types can also improve usability.

**2. Differentiate between client-side and server-side validation.**  
Client-side validation takes place before data is sent to the server. Server-side validation takes place on the server after the application submits the data.

**3. State two differences between Fetch and Axios.**  
Fetch is built into JavaScript, while Axios is an external library. The notes describe Fetch as requiring manual JSON parsing and Axios as providing automatic JSON conversion.

**4. State two benefits of data caching.**  
Caching improves loading speed and reduces internet usage. It also supports a better offline experience.

### C. Five-mark questions (4 × 5)

**1. Explain controlled and uncontrolled components with examples and differences.**  
A controlled component uses React state to manage the input value. The notes show `value={email}` and `onChangeText={setEmail}` to connect a TextInput to state. This makes validation, data handling, and real-time updates easier. An uncontrolled component handles its value directly without state management; the PDF gives `defaultValue="Hello"` as an example. Controlled components offer better validation and dynamic updates, while uncontrolled components are simpler to implement but provide more limited control.

**2. Explain form handling and form validation in React Native.**  
Form handling manages user input forms such as login, registration, and feedback forms. A basic form can use TextInput fields for username and password, state to store their values, and a Button to submit. The password field can use `secureTextEntry={true}`. Form libraries named in the notes are Formik and React Hook Form. Form validation checks whether input is correct, complete, and properly formatted. Client-side validation occurs before submission to the server; server-side validation occurs after submission. Email format and password rules are examples. Validation prevents invalid data, improves security, and enhances user experience.

**3. Explain REST APIs and compare Fetch API with Axios.**  
An API enables communication between mobile applications, servers, and databases. REST means Representational State Transfer and describes a web service architecture that communicates over HTTP. GET retrieves data, POST creates data, PUT updates data, and DELETE removes data. Fetch is built into JavaScript and supports promises. A GET request can convert a response to JSON, and a POST request can send a JSON body. Axios is an external HTTP client library. The notes list cleaner syntax, better error handling, request cancellation support, and automatic JSON conversion as Axios advantages. Fetch is built in, while Axios must be installed as a package.

**4. Explain AsyncStorage, data caching, and offline handling.**  
AsyncStorage is a local storage system that stores data persistently inside a mobile application. It can store login tokens, user preferences, and offline data. The notes show `setItem()` to store a value, `getItem()` to retrieve it, and `removeItem()` to remove it. AsyncStorage is simple and supports persistent and offline storage, but it is not suitable for large databases and has limited security. Data caching temporarily stores frequently used data to improve performance. It speeds up loading and reduces internet use. An offline strategy stores data locally, displays cached data when the internet is unavailable, and synchronizes data when the connection returns.

---

# Unit 5 — Authentication and Backend Integration

## 1. Introduction to backend services

The **backend** is the server-side part of an application. It handles data storage, authentication, business logic, database operations, and API management. It communicates with the mobile application and processes user requests.

Backend services help mobile applications store user data, manage authentication, process API requests, synchronize data, and handle cloud storage. The PDF gives login systems, online shopping applications, chat applications, and banking systems as examples.

### Types of backend services

1. **Traditional backend:** developers create their own server, APIs, and database systems. Technologies named in the notes include Node.js, PHP, Django, and Spring Boot.
2. **Backend as a Service (BaaS):** a cloud platform provides ready-made backend services. Examples include Firebase, Supabase, and AWS Amplify.

The notes list faster development, easy scalability, secure data handling, and real-time synchronization as advantages of backend services.

## 2. Introduction to Firebase

**Firebase** is a Backend as a Service (BaaS) platform developed by Google.

### Firebase features

1. **Authentication:** supports email/password, phone, Google, and Facebook login.
2. **Realtime Database:** stores and synchronizes data in real time.
3. **Firestore Database:** a modern NoSQL cloud database.
4. **Cloud Storage:** stores images, videos, and documents.
5. **Analytics:** tracks user activity and application performance.

### Advantages

- Easy integration
- Real-time synchronization
- Secure authentication
- Cloud-based storage
- Scalable infrastructure

### Limitations

- Vendor dependency
- Limited customization
- Pricing may increase for large-scale applications

## 3. Firebase project setup and configuration

The PDF lists these project creation steps:

1. Open Firebase Console.
2. Create a new project.
3. Register the Android application.
4. Download the configuration files.

Install the Firebase package with:

```bash
npm install firebase
```

### Firebase configuration example

The notes show importing `initializeApp`, creating a configuration object, and initializing the Firebase application:

```jsx
import { initializeApp } from 'firebase/app';

const firebaseConfig = {
  apiKey: 'YOUR_API_KEY',
  authDomain: 'YOUR_DOMAIN',
  projectId: 'YOUR_PROJECT_ID',
};

const app = initializeApp(firebaseConfig);
```

Firebase Console supports database management, authentication settings, and monitoring application usage. Proper configuration supports secure communication, correct API integration, and a stable backend connection.

## 4. User authentication

**Authentication** is the process of verifying a user's identity. The PDF gives login systems, OTP verification, and biometric authentication as examples.

### Types of authentication

1. **Email and password authentication:** users sign in with an email address and password.
2. **Phone authentication:** users verify their identity through OTP and SMS verification.
3. **Social authentication:** users sign in through services such as Google Login or Facebook Login.

Authentication helps protect user data, restrict unauthorized access, and maintain user privacy.

## 5. Email and password authentication using Firebase

The notes demonstrate three operations: account creation, login, and logout.

### Creating a user account

The PDF uses `createUserWithEmailAndPassword()` from `firebase/auth`:

```jsx
import {
  getAuth,
  createUserWithEmailAndPassword,
} from 'firebase/auth';

const auth = getAuth();

createUserWithEmailAndPassword(
  auth,
  'user@gmail.com',
  'password123'
)
  .then((userCredential) => {
    console.log('User Created');
  })
  .catch((error) => {
    console.log(error.message);
  });
```

### User login

The PDF uses `signInWithEmailAndPassword()`:

```jsx
import { signInWithEmailAndPassword } from 'firebase/auth';

signInWithEmailAndPassword(auth, 'user@gmail.com', 'password123')
  .then((userCredential) => {
    console.log('Login Successful');
  })
  .catch((error) => {
    console.log(error.message);
  });
```

### User logout

The PDF uses `signOut()`:

```jsx
import { signOut } from 'firebase/auth';

signOut(auth);
```

### Common authentication errors

| Error | Reason given in the notes |
|---|---|
| Invalid email | Incorrect email format |
| Weak password | Password too short |
| User not found | Account does not exist |
| Wrong password | Incorrect password |

### Best practices

- Use strong passwords.
- Enable email verification.
- Use secure token storage.
- Implement session timeout.

## 6. OTP and phone authentication

**OTP** stands for **One-Time Password**. OTP authentication verifies users through temporary codes sent to their mobile numbers.

### Workflow

1. The user enters a phone number.
2. The server sends an OTP.
3. The user enters the OTP.
4. The system verifies the OTP.
5. Login succeeds after verification.

Firebase supports SMS-based verification and automatic OTP detection, according to the PDF.

**Advantages:** higher security, fast login, and less dependence on passwords.

**Limitations:** requires network connectivity, SMS delivery may be delayed, and SIM swapping creates a risk.

## 7. Firebase Realtime Database

**Firebase Realtime Database** is a cloud-hosted NoSQL database. It stores data in JSON format and synchronizes data in real time.

### Features

- Real-time synchronization
- Offline support
- Cloud-hosted storage
- Fast updates

### Data structure

The PDF shows a JSON-style structure:

```json
{
  "users": {
    "101": {
      "name": "Rahul"
    }
  }
}
```

### Writing data

The notes use `getDatabase`, `ref`, and `set`:

```jsx
import { getDatabase, ref, set } from 'firebase/database';

const db = getDatabase();

set(ref(db, 'users/101'), {
  name: 'Rahul',
});
```

**Advantages:** instant updates, suitability for chat applications, and easy synchronization.

**Limitations:** complex querying and limited scalability for structured data, as stated in the notes.

## 8. Firestore Database

**Firestore** is Firebase's modern cloud NoSQL database. It organizes data using **collections** and **documents**.

The PDF illustrates a Users collection containing a user document with fields such as Name and Email.

### Adding data to Firestore

The notes use `getFirestore`, `collection`, and `addDoc`:

```jsx
import {
  getFirestore,
  collection,
  addDoc,
} from 'firebase/firestore';

const db = getFirestore();

addDoc(collection(db, 'users'), {
  name: 'Rahul',
});
```

The PDF lists better scalability, advanced querying, and structured data organization as Firestore advantages.

### Firestore versus Realtime Database

| Firestore | Realtime Database |
|---|---|
| Collection-based | JSON-tree structure |
| Better scalability in the notes' comparison | Faster synchronization in the notes' comparison |
| Advanced queries | Simpler structure |

## 9. CRUD operations with Firebase

**CRUD** stands for:

- **Create:** add new data.
- **Read:** retrieve existing data.
- **Update:** modify existing data.
- **Delete:** remove data.

The PDF provides these Firestore examples:

```jsx
// Create
addDoc(collection(db, 'users'), {
  name: 'Amit',
});

// Read
getDocs(collection(db, 'users'));

// Update
updateDoc(doc(db, 'users', id), {
  name: 'Rahul',
});

// Delete
deleteDoc(doc(db, 'users', id));
```

CRUD operations allow an application to manage user data, modify records, and remove unnecessary data.

## 10. Secure data handling and Firebase authentication rules

Mobile applications may handle passwords, personal information, and payment details. Poor security can lead to data theft, unauthorized access, and privacy violations.

Firebase Security Rules allow developers to define who can access data. The notes give this example to allow access only when a user is authenticated:

```text
allow read, write: if request.auth != null;
```

### Best security practices

1. Use HTTPS communication.
2. Never store plain passwords.
3. Validate user inputs.
4. Restrict database access.
5. Use secure authentication tokens.

## 11. Token management and session handling

A **token** is a secure digital key used for authentication and session validation.

**Session handling** maintains a user's login status after authentication.

### JWT

**JWT** stands for **JSON Web Token**. The notes state that JWT is widely used for secure authentication. Its three parts are:

1. Header
2. Payload
3. Signature

### Benefits of token-based authentication

- Secure communication
- Stateless authentication
- Better scalability

The PDF lists AsyncStorage and secure storage libraries as token storage options.

### Risks of poor token management

- Session hijacking
- Unauthorized access
- Security vulnerabilities

## 12. Testing mobile applications

Testing checks application reliability, functionality, and performance.

### Types of testing

1. **Unit testing:** tests individual components or functions.
2. **Manual testing:** users or testers test the application manually.
3. **Integration testing:** tests communication between modules.
4. **UI testing:** tests user-interface functionality.

### Tools listed in the PDF

- Jest
- React Native Testing Library
- Detox

Testing can detect bugs early, improve application quality, and reduce crashes.

## 13. Building APK and AAB for Android

### APK

**APK** stands for **Android Package Kit**. It is an installation file for Android applications.

### AAB

**AAB** stands for **Android App Bundle**. The notes describe it as the modern publishing format recommended by Google Play Store.

The PDF shows this command for running on Android:

```bash
npx react-native run-android
```

For a release APK, the notes show:

```bash
cd android
gradlew assembleRelease
```

The PDF gives this output folder:

```text
android/app/build/outputs/apk/release/
```

Release builds improve performance, reduce debugging information, and optimize application size.

## 14. Deployment process overview

The PDF lists these deployment steps:

1. Generate a signed APK/AAB.
2. Create a Google Play Console account.
3. Upload the application.
4. Add application details.
5. Submit the application for review.

### Information required for deployment

- App name
- Screenshots
- Privacy policy
- App icon
- Description

### Google Play Store review

The notes state that Google checks security, privacy, and policy compliance.

### Deployment challenges

- Application crashes
- Permission issues
- Policy violations

## Unit 5 — Quick revision

- The backend handles data storage, authentication, business logic, database operations, and API management.
- Traditional backends use custom servers, APIs, and databases; BaaS provides ready-made cloud services.
- Firebase is Google's BaaS platform.
- Firebase includes Authentication, Realtime Database, Firestore, Cloud Storage, and Analytics.
- Authentication verifies user identity through email/password, phone/OTP, or social login.
- Firebase Authentication examples use create, sign-in, and sign-out methods.
- OTP uses a temporary code sent to a mobile number.
- Realtime Database stores JSON data; Firestore organizes collections and documents.
- CRUD means Create, Read, Update, and Delete.
- Firebase Security Rules control data access.
- JWT contains a header, payload, and signature.
- Testing types include unit, manual, integration, and UI testing.
- APK is an Android installation package; AAB is a publishing format.
- Deployment includes signing, uploading, adding app details, and review.

## Unit 5 — Question bank with model answers

### A. One-mark questions (8 × 1)

**1. What is a backend?**  
The backend is the server-side part of an application that handles data storage, authentication, business logic, database operations, and API management.

**2. What does BaaS stand for?**  
Backend as a Service.

**3. Who developed Firebase?**  
Google.

**4. What is authentication?**  
Authentication is the process of verifying a user's identity.

**5. What does OTP stand for?**  
One-Time Password.

**6. What data format does Firebase Realtime Database use?**  
JSON format.

**7. What does CRUD stand for?**  
Create, Read, Update, and Delete.

**8. What does JWT stand for?**  
JSON Web Token.

### B. Two-mark questions (4 × 2)

**1. Differentiate between a traditional backend and BaaS.**  
A traditional backend requires developers to create a custom server, APIs, and database systems. BaaS provides ready-made backend services through a cloud platform.

**2. State two advantages and two limitations of Firebase.**  
Advantages include easy integration and real-time synchronization. Limitations include vendor dependency and limited customization. The notes also mention that costs may increase for large-scale applications.

**3. Explain the OTP authentication process.**  
The user enters a phone number, the server sends an OTP, and the user enters the received code. The system verifies the code and allows login after successful verification.

**4. What are the four types of mobile application testing listed in the PDF?**  
Unit testing, manual testing, integration testing, and UI testing.

### C. Five-mark questions (4 × 5)

**1. Explain Firebase and its main features, advantages, and limitations.**  
Firebase is Google's Backend as a Service platform. Its features include Authentication for user login, Realtime Database for real-time data synchronization, Firestore as a NoSQL cloud database, Cloud Storage for images/videos/documents, and Analytics for tracking user activity and application performance. Its advantages include easy integration, real-time synchronization, secure authentication, cloud storage, and scalable infrastructure. Its limitations include vendor dependency, limited customization, and potentially higher pricing for large-scale applications.

**2. Explain the different authentication methods and the Firebase email/password authentication process.**  
Authentication verifies a user's identity. The notes list email/password authentication, phone authentication using OTP/SMS, and social authentication such as Google or Facebook Login. In Firebase email/password authentication, `createUserWithEmailAndPassword()` creates a user account. `signInWithEmailAndPassword()` logs a user in. `signOut()` logs a user out. The notes also list common errors such as invalid email, weak password, user not found, and wrong password. Best practices include strong passwords, email verification, secure token storage, and session timeout.

**3. Compare Firebase Realtime Database and Firestore, and explain CRUD operations.**  
Realtime Database is a cloud-hosted NoSQL database that stores data in JSON format and synchronizes it in real time. Firestore is a modern NoSQL database that organizes data into collections and documents. The PDF compares Realtime Database as a simpler JSON tree with faster synchronization, while Firestore provides better scalability and advanced queries. CRUD operations mean Create, Read, Update, and Delete. In the notes, Create uses `addDoc()`, Read uses `getDocs()`, Update uses `updateDoc()`, and Delete uses `deleteDoc()`. These operations manage, retrieve, modify, and remove application records.

**4. Explain secure data handling, token management, testing, and deployment.**  
Mobile applications may store passwords, user information, and payment details, so security matters. The PDF recommends HTTPS, never storing plain passwords, validating user input, restricting database access, and using secure authentication tokens. A token is a digital key for authentication and session validation. JWT contains a header, payload, and signature. Poor token handling can cause session hijacking and unauthorized access. Testing includes unit, manual, integration, and UI testing, using tools such as Jest, React Native Testing Library, and Detox. Android deployment involves generating a signed APK/AAB, uploading it to Google Play Console, entering app details, and submitting it for review. Google checks security, privacy, and policy compliance.

---

# Final revision checklist

Use this checklist to make sure you have revised all five source units.

## Unit 1 — Fundamentals

- [ ] Define mobile application development.
- [ ] Compare native, web, and cross-platform applications.
- [ ] Explain why cross-platform development is needed.
- [ ] Define React Native and list its features.
- [ ] Explain advantages and limitations of React Native.
- [ ] Explain JavaScript Thread, Native Thread, and Bridge.
- [ ] List setup prerequisites and compare Expo CLI with React Native CLI.
- [ ] Explain the project structure.
- [ ] Compare functional and class components.
- [ ] Define JSX and explain its rules.
- [ ] Compare inline styling and StyleSheet API.
- [ ] Differentiate props and state.
- [ ] Explain event handling, user input, and debugging tools.

## Unit 2 — Adaptive UI

- [ ] Differentiate UI and UX.
- [ ] Explain the five UI/UX principles.
- [ ] Explain Flexbox and its four important properties.
- [ ] Describe the Dimensions API.
- [ ] Compare Android and iOS design conventions from the notes.
- [ ] Explain Platform API and platform-specific files.
- [ ] Explain portrait/landscape handling.
- [ ] Describe theming, dark mode, and Appearance API.
- [ ] Explain custom fonts and icons.
- [ ] Explain accessibilityLabel, accessible, TalkBack, and VoiceOver.
- [ ] Revise user-friendly interface best practices.

## Unit 3 — Navigation and state

- [ ] Define navigation and React Navigation.
- [ ] Compare stack, tab, and drawer navigation.
- [ ] Explain NavigationContainer.
- [ ] Explain mounting, updating, unmounting, and navigation events.
- [ ] Explain passing and receiving screen parameters.
- [ ] Define nested navigation.
- [ ] Differentiate local and global state.
- [ ] Explain Context API and prop drilling.
- [ ] Name solutions for complex state.
- [ ] Explain React.memo, useMemo, useCallback, lazy loading, and FlatList optimization.

## Unit 4 — Data and APIs

- [ ] Define data handling and explain its importance.
- [ ] Explain TextInput and input optimization.
- [ ] Compare controlled and uncontrolled components.
- [ ] Explain form handling and validation.
- [ ] Differentiate client-side and server-side validation.
- [ ] Define API and REST API.
- [ ] Memorize GET, POST, PUT, and DELETE purposes.
- [ ] Explain Fetch and Axios; compare them.
- [ ] Explain loading states, errors, and user feedback.
- [ ] Explain AsyncStorage operations and limitations.
- [ ] Explain caching and offline strategy.

## Unit 5 — Backend and deployment

- [ ] Define backend and compare traditional backend with BaaS.
- [ ] Define Firebase and list its services.
- [ ] Explain Firebase setup and configuration.
- [ ] Explain email/password, phone/OTP, and social authentication.
- [ ] Explain Firebase account creation, login, and logout.
- [ ] Explain Realtime Database and Firestore structures.
- [ ] Compare Realtime Database with Firestore.
- [ ] Explain CRUD operations.
- [ ] Explain Firebase Security Rules and security practices.
- [ ] Explain tokens, sessions, and JWT structure.
- [ ] Explain testing types and tools.
- [ ] Differentiate APK and AAB.
- [ ] Memorize the deployment steps and common challenges.

---

## Source coverage and notes

This guide draws from the uploaded PDFs in their supplied order:

| Unit | Source PDF | Unit title in the PDF |
|---|---|---|
| 1 | `ch-1.pdf` | Introduction to React Native Fundamentals |
| 2 | `ch-2.pdf` | Adaptive User Interface Design |
| 3 | `ch-3.pdf` | Navigation & State Management |
| 4 | `ch-4.pdf` | Data Handling & API Integration |
| 5 | `ch-5.pdf` | Authentication & Backend Integration |

The unit notes preserve the topics and comparisons in these PDFs. The model answers reorganize the supplied material into exam-answer form. Where the source gives only a brief code example or short definition, this guide does not add unrelated syllabus topics.
