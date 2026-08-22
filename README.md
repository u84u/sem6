# React Native Practical Exam: Complete Guide

A cleaned-up, consistently formatted version of your guide is below. I also fixed the Markdown structure and code formatting while keeping the actual practical content intact.

## React Native Practical Exam

This guide covers all 15 practical topics. Complete **Step 0** once. For each practical afterward, replace the contents of `App.js` with the provided code and run the app.

At the end, there is a quick cheat sheet for the exam.

---

# Step 0: One-Time Setup

Complete this once before starting the practicals.

### 1. Open VS Code

Open VS Code on the college computer.

### 2. Open the Terminal

In VS Code, go to:

**Terminal → New Terminal**

A terminal will appear at the bottom of the window.

### 3. Check Node.js

Run:

```bash
node -v
```

If you see a version number such as:

```text
v18.17.0
```

Node.js is installed.

If you get a `"not recognized"` error, contact the lab administrator or invigilator.

### 4. Create the Expo Project

Run:

```bash
npx create-expo-app MyPractical
```

Wait for the project to finish downloading and installing.

### 5. Enter the Project Directory

```bash
cd MyPractical
```

### 6. Open the Project in VS Code

Go to:

**File → Open Folder → MyPractical → Select Folder**

VS Code will reload with the project files visible in the sidebar.

### 7. Install Expo Go

On your phone, install **Expo Go** from the Play Store or App Store.

You can use Expo Go to preview your React Native application on your phone.

### 8. Start the Development Server

Run:

```bash
npm start
```

A QR code will appear.

Open **Expo Go** on your phone and scan the QR code.

Alternatively, press:

```text
w
```

in the terminal to open the application in a web browser.

> **Setup complete.**

For every practical below, you only need to modify `App.js`.

---

# How to Replace the Code

For each practical:

1. Open `App.js` in VS Code.
2. Press `Ctrl + A`.
3. Press `Delete`.
4. Paste the code for the practical.
5. Press `Ctrl + S`.
6. Check your phone or browser.

Expo should automatically reload the application.

---

# Practical 1: Installation & Setup

This practical is already completed in **Step 0**.

If you are asked to demonstrate installation, show:

* The `create-expo-app` command.
* The project directory.
* The running Expo development server.
* The application running on Expo Go or the browser.

The alternative React Native CLI approach exists:

```bash
npx react-native init MyPractical
```

However, Expo is simpler for this practical setup.

---

# Practical 2: Basic App

### Text, Image, and Button

Replace `App.js` with:

```tsx
import React from 'react';
import { Alert, Button, Image, Text, View } from 'react-native';

export default function App() {
  return (
    <View
      style={{
        flex: 1,
        justifyContent: 'center',
        alignItems: 'center',
      }}
    >
      <Text>Hello React Native</Text>

      <Image
        source={{
          uri: 'https://reactnative.dev/img/tiny_logo.png',
        }}
        style={{
          width: 100,
          height: 100,
        }}
      />

      <Button
        title="Click Me"
        onPress={() => Alert.alert('Pressed')}
      />
    </View>
  );
}
```

### Expected Result

You should see:

* Text saying **Hello React Native**
* A React Native logo
* A **Click Me** button
* An alert when the button is pressed

---

# Practical 3: UI Design Using Core Components

### ScrollView

```tsx
import React from 'react';
import { ScrollView, Text, View } from 'react-native';

export default function App() {
  return (
    <ScrollView>
      <View style={{ padding: 20 }}>
        <Text>Item 1</Text>
        <Text>Item 2</Text>
        <Text>Item 3</Text>
      </View>
    </ScrollView>
  );
}
```

---

# Practical 4: Styling Using StyleSheet and Flexbox

```tsx
import React from 'react';
import { StyleSheet, Text, View } from 'react-native';

export default function App() {
  return (
    <View style={styles.container}>
      <Text style={styles.text}>Styled Text</Text>
    </View>
  );
}

const styles = StyleSheet.create({
  container: {
    flex: 1,
    justifyContent: 'center',
    alignItems: 'center',
  },

  text: {
    fontSize: 20,
    color: 'blue',
  },
});
```

---

# Practical 5: User Input Form Creation

```tsx
import React, { useState } from 'react';
import { Alert, Button, TextInput, View } from 'react-native';

export default function App() {
  const [name, setName] = useState('');

  return (
    <View style={{ padding: 40 }}>
      <TextInput
        placeholder="Enter Name"
        value={name}
        onChangeText={setName}
        style={{
          borderWidth: 1,
          marginBottom: 10,
          padding: 8,
        }}
      />

      <Button
        title="Submit"
        onPress={() => Alert.alert(name)}
      />
    </View>
  );
}
```

### Expected Result

Enter a name and press **Submit**.

The entered name will appear in an alert.

---

# Practical 6: Props and State in Functional Components

```tsx
import React from 'react';
import { Text, View } from 'react-native';

const Child = ({ message }) => {
  return <Text>{message}</Text>;
};

export default function App() {
  return (
    <View style={{ padding: 40 }}>
      <Child message="Hello from Parent" />
    </View>
  );
}
```

### Key Concept

The parent component passes data to the child using **props**:

```tsx
<Child message="Hello from Parent" />
```

The child receives it using:

```tsx
const Child = ({ message }) => {
```

---

# Practical 7: Counter App Using State

```tsx
import React, { useState } from 'react';
import { Button, Text, View } from 'react-native';

export default function App() {
  const [count, setCount] = useState(0);

  return (
    <View
      style={{
        flex: 1,
        justifyContent: 'center',
        alignItems: 'center',
      }}
    >
      <Text style={{ fontSize: 24 }}>{count}</Text>

      <Button
        title="Increase"
        onPress={() => setCount(count + 1)}
      />
    </View>
  );
}
```

### Key Concept

`useState()` stores the counter value:

```tsx
const [count, setCount] = useState(0);
```

The value is increased using:

```tsx
setCount(count + 1);
```

---

# Practical 8: Stack Navigation

## Step 1: Install Navigation

Run this inside the project directory:

```bash
npx expo install @react-navigation/native @react-navigation/stack react-native-screens react-native-safe-area-context
```

## Step 2: Replace `App.js`

```tsx
import React from 'react';
import { Button, Text, View } from 'react-native';
import { NavigationContainer } from '@react-navigation/native';
import { createStackNavigator } from '@react-navigation/stack';

const Stack = createStackNavigator();

function Home({ navigation }) {
  return (
    <View
      style={{
        flex: 1,
        justifyContent: 'center',
        alignItems: 'center',
      }}
    >
      <Button
        title="Go"
        onPress={() => navigation.navigate('Details')}
      />
    </View>
  );
}

function Details() {
  return (
    <View
      style={{
        flex: 1,
        justifyContent: 'center',
        alignItems: 'center',
      }}
    >
      <Text>Details Screen</Text>
    </View>
  );
}

export default function App() {
  return (
    <NavigationContainer>
      <Stack.Navigator>
        <Stack.Screen
          name="Home"
          component={Home}
        />

        <Stack.Screen
          name="Details"
          component={Details}
        />
      </Stack.Navigator>
    </NavigationContainer>
  );
}
```

### Expected Result

The app starts on the **Home** screen.

Pressing **Go** navigates to the **Details** screen.

---

# Practical 9: Tab Navigation

## Step 1: Install Bottom Tabs

```bash
npx expo install @react-navigation/bottom-tabs
```

## Step 2: Replace `App.js`

```tsx
import React from 'react';
import { Text, View } from 'react-native';
import { NavigationContainer } from '@react-navigation/native';
import { createBottomTabNavigator } from '@react-navigation/bottom-tabs';

const Tab = createBottomTabNavigator();

function Home() {
  return (
    <View
      style={{
        flex: 1,
        justifyContent: 'center',
        alignItems: 'center',
      }}
    >
      <Text>Home Tab</Text>
    </View>
  );
}

function Profile() {
  return (
    <View
      style={{
        flex: 1,
        justifyContent: 'center',
        alignItems: 'center',
      }}
    >
      <Text>Profile Tab</Text>
    </View>
  );
}

export default function App() {
  return (
    <NavigationContainer>
      <Tab.Navigator>
        <Tab.Screen
          name="Home"
          component={Home}
        />

        <Tab.Screen
          name="Profile"
          component={Profile}
        />
      </Tab.Navigator>
    </NavigationContainer>
  );
}
```

### Expected Result

Two tabs appear at the bottom:

* Home
* Profile

Tap either tab to switch screens.

---

# Practical 10: Passing Data Between Screens

This practical uses the Stack Navigator from Practical 8.

If necessary, install the navigation packages again:

```bash
npx expo install @react-navigation/native @react-navigation/stack react-native-screens react-native-safe-area-context
```

### `App.js`

```tsx
import React from 'react';
import { Button, Text, View } from 'react-native';
import { NavigationContainer } from '@react-navigation/native';
import { createStackNavigator } from '@react-navigation/stack';

const Stack = createStackNavigator();

function Home({ navigation }) {
  return (
    <View
      style={{
        flex: 1,
        justifyContent: 'center',
        alignItems: 'center',
      }}
    >
      <Button
        title="Send Name"
        onPress={() =>
          navigation.navigate('Details', {
            name: 'John',
          })
        }
      />
    </View>
  );
}

function Details({ route }) {
  return (
    <View
      style={{
        flex: 1,
        justifyContent: 'center',
        alignItems: 'center',
      }}
    >
      <Text>
        Received: {route.params.name}
      </Text>
    </View>
  );
}

export default function App() {
  return (
    <NavigationContainer>
      <Stack.Navigator>
        <Stack.Screen
          name="Home"
          component={Home}
        />

        <Stack.Screen
          name="Details"
          component={Details}
        />
      </Stack.Navigator>
    </NavigationContainer>
  );
}
```

### Key Concept

Data is passed during navigation:

```tsx
navigation.navigate('Details', {
  name: 'John',
});
```

The receiving screen accesses it through:

```tsx
route.params.name
```

---

# Practical 11: Global State Using Context API

```tsx
import React, {
  createContext,
  useContext,
  useState,
} from 'react';
import { Text, View } from 'react-native';

const MyContext = createContext();

function Child() {
  const user = useContext(MyContext);

  return <Text>User: {user}</Text>;
}

export default function App() {
  const [user] = useState('John');

  return (
    <MyContext.Provider value={user}>
      <View
        style={{
          flex: 1,
          justifyContent: 'center',
          alignItems: 'center',
        }}
      >
        <Child />
      </View>
    </MyContext.Provider>
  );
}
```

### Key Concept

The `Provider` makes the value available to child components:

```tsx
<MyContext.Provider value={user}>
```

The child accesses it using:

```tsx
useContext(MyContext);
```

---

# Practical 12: API Integration Using Fetch

```tsx
import React, {
  useEffect,
  useState,
} from 'react';
import {
  FlatList,
  Text,
  View,
} from 'react-native';

export default function App() {
  const [posts, setPosts] = useState([]);

  useEffect(() => {
    fetch('https://jsonplaceholder.typicode.com/posts')
      .then((res) => res.json())
      .then((data) => setPosts(data.slice(0, 10)));
  }, []);

  return (
    <View
      style={{
        padding: 20,
        marginTop: 30,
      }}
    >
      <FlatList
        data={posts}
        keyExtractor={(item) => item.id.toString()}
        renderItem={({ item }) => (
          <Text>{item.title}</Text>
        )}
      />
    </View>
  );
}
```

### Expected Result

The application fetches data from the internet and displays the first 10 post titles.

> **Internet access is required for this practical.**

---

# Practical 13: Form Validation

```tsx
import React, { useState } from 'react';
import {
  Alert,
  Button,
  Text,
  TextInput,
  View,
} from 'react-native';

export default function App() {
  const [name, setName] = useState('');
  const [error, setError] = useState('');

  const handleSubmit = () => {
    if (name === '') {
      setError('Name is required');
    } else {
      setError('');
      Alert.alert('Submitted: ' + name);
    }
  };

  return (
    <View style={{ padding: 40 }}>
      <TextInput
        placeholder="Enter Name"
        value={name}
        onChangeText={setName}
        style={{
          borderWidth: 1,
          marginBottom: 10,
          padding: 8,
        }}
      />

      {error !== '' && (
        <Text style={{ color: 'red' }}>
          {error}
        </Text>
      )}

      <Button
        title="Submit"
        onPress={handleSubmit}
      />
    </View>
  );
}
```

### Expected Result

If the input is empty and **Submit** is pressed:

```text
Name is required
```

appears in red.

If a name is entered, an alert displays the submitted name.

---

# Practical 14: Firebase Authentication

This practical requires a Firebase project and internet access.

It is more setup-heavy than the other practicals.

## Step 1: Install Firebase

```bash
npx expo install firebase
```

## Step 2: Create a Firebase Project

Open:

[Firebase Console](https://console.firebase.google.com/?utm_source=chatgpt.com)

Then:

1. Create a Firebase project.
2. Open **Project Settings**.
3. Add a **Web App**.
4. Copy the Firebase configuration.
5. Enable **Authentication**.
6. Open **Sign-in method**.
7. Enable **Email/Password**.

## Step 3: Replace `App.js`

```tsx
import React, { useState } from 'react';
import {
  Button,
  Text,
  TextInput,
  View,
} from 'react-native';
import { initializeApp } from 'firebase/app';
import {
  createUserWithEmailAndPassword,
  getAuth,
} from 'firebase/auth';

const firebaseConfig = {
  apiKey: 'YOUR_API_KEY',
  authDomain: 'YOUR_PROJECT.firebaseapp.com',
  projectId: 'YOUR_PROJECT',
};

const app = initializeApp(firebaseConfig);
const auth = getAuth(app);

export default function App() {
  const [email, setEmail] = useState('');
  const [password, setPassword] = useState('');
  const [message, setMessage] = useState('');

  const handleSignUp = () => {
    createUserWithEmailAndPassword(
      auth,
      email,
      password,
    )
      .then(() => {
        setMessage('Account created!');
      })
      .catch((err) => {
        setMessage(err.message);
      });
  };

  return (
    <View
      style={{
        padding: 40,
        marginTop: 40,
      }}
    >
      <TextInput
        placeholder="Email"
        value={email}
        onChangeText={setEmail}
        style={{
          borderWidth: 1,
          marginBottom: 10,
          padding: 8,
        }}
      />

      <TextInput
        placeholder="Password"
        value={password}
        onChangeText={setPassword}
        secureTextEntry
        style={{
          borderWidth: 1,
          marginBottom: 10,
          padding: 8,
        }}
      />

      <Button
        title="Sign Up"
        onPress={handleSignUp}
      />

      <Text>{message}</Text>
    </View>
  );
}
```

> If the exam only requires explaining or showing the Firebase authentication implementation rather than demonstrating a live Firebase project, the code and configuration steps may be sufficient. Confirm the exact requirement with the examiner.

---

# Practical 15: AsyncStorage

AsyncStorage provides local persistent storage for simple key-value data.

## Step 1: Install AsyncStorage

```bash
npx expo install @react-native-async-storage/async-storage
```

## Step 2: Replace `App.js`

```tsx
import React, { useState } from 'react';
import {
  Button,
  Text,
  TextInput,
  View,
} from 'react-native';
import AsyncStorage from '@react-native-async-storage/async-storage';

export default function App() {
  const [name, setName] = useState('');
  const [saved, setSaved] = useState('');

  const saveName = async () => {
    await AsyncStorage.setItem('name', name);
    setSaved('Saved!');
  };

  const loadName = async () => {
    const value = await AsyncStorage.getItem('name');
    setSaved('Stored value: ' + value);
  };

  return (
    <View
      style={{
        padding: 40,
        marginTop: 40,
      }}
    >
      <TextInput
        placeholder="Enter Name"
        value={name}
        onChangeText={setName}
        style={{
          borderWidth: 1,
          marginBottom: 10,
          padding: 8,
        }}
      />

      <Button
        title="Save"
        onPress={saveName}
      />

      <Button
        title="Load"
        onPress={loadName}
      />

      <Text>{saved}</Text>
    </View>
  );
}
```

### Expected Result

1. Enter a name.
2. Press **Save**.
3. Press **Load**.
4. The stored value appears.

The data is stored locally, so an internet connection is not required.

---

# Quick Exam Cheat Sheet

| Task                 | Command / Action                  |
| -------------------- | --------------------------------- |
| Open terminal        | `Ctrl + ~`                        |
| Start app            | `npm start`                       |
| Open web preview     | Press `w`                         |
| Use Expo Go          | Scan the QR code                  |
| Stop server          | `Ctrl + C`                        |
| Save file            | `Ctrl + S`                        |
| Select all code      | `Ctrl + A`                        |
| Install Expo package | `npx expo install <package>`      |
| Create Expo project  | `npx create-expo-app MyPractical` |
| Enter project        | `cd MyPractical`                  |
| Git stage files      | `git add .`                       |
| Git commit           | `git commit -m "message"`         |
| Push to GitHub       | `git push`                        |

---

# Practical-to-Concept Map

| Practical | Main Concept                   |
| --------- | ------------------------------ |
| 1         | Installation and Expo setup    |
| 2         | Text, Image, Button            |
| 3         | ScrollView and core components |
| 4         | StyleSheet and Flexbox         |
| 5         | TextInput and forms            |
| 6         | Props                          |
| 7         | State with `useState`          |
| 8         | Stack Navigation               |
| 9         | Tab Navigation                 |
| 10        | Passing data between screens   |
| 11        | Context API                    |
| 12        | API integration with `fetch`   |
| 13        | Form validation                |
| 14        | Firebase Authentication        |
| 15        | AsyncStorage                   |

## The basic exam workflow

```text
Create project
     ↓
npm start
     ↓
Open App.js
     ↓
Ctrl + A
     ↓
Paste practical code
     ↓
Ctrl + S
     ↓
Check Expo Go / Browser
     ↓
Demonstrate result
     ↓
Move to next practical
```
