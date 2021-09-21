# VS Code Snippets
My Snippets files for Visual Studio Code

## 🚀 Getting Started
Below are the snippets already made

### 🟨 JavaScript Snippets

<details>
<summary>arrf</summary>
  
- Create JavaScript arrow function
```js
// arrf: JavaScript Arrow Function

const funcName = (param) => {
    
}
```
</details>


### ⚛️ Expo/React Native Snippets

<details>
<summary>rnapp</summary>
  
- Create React Native App.js
```js
// rnapp: React Native App.js

import React from 'react';
import { NavigationContainer } from '@react-navigation/native';
import { createNativeStackNavigator } from '@react-navigation/native-stack';
import useCachedFonts from './src/hooks/useCachedFonts';

import StartScreen from './src/screens/StartScreen';

const Stack = createNativeStackNavigator();

export default function App() {
    const isLoadingComplete = useCachedFonts();

    if (!isLoadingComplete) {
        return null;
    } else {
        return (
            <NavigationContainer>
                <Stack.Navigator
                    screenOptions={{
                        headerShown: false,
                        headerBackVisible: false,
                        headerBackTitleVisible: false,
                    }}
                initialRouteName="Start"
            >
                <Stack.Screen
                    name="Start"
                    component={StartScreen}
                />
                </Stack.Navigator>
            </NavigationContainer>
        );
    }
}
```
</details>


<details>
<summary>rnfonts</summary>
  
- Create load fonts hook
```js
// rnfonts: React Native load fonts

import { useEffect, useState } from 'react';
import * as SplashScreen from 'expo-splash-screen';
import * as Font from 'expo-font';

export default function useCachedFonts() {
    const [areFontsLoaded, setFontsLoaded] = useState(false);

    useEffect(() => {
        async function loadFonts() {
            try {
                SplashScreen.preventAutoHideAsync();

                await Font.loadAsync({
                    'Font-Name': require('../assets/fonts/Font-Name.ttf'),
                });
            }

            catch (e) {
                console.warn(e);
            }

            finally {
                setFontsLoaded(true);
                SplashScreen.hideAsync();
            }
        }

        loadFonts();
    }, []);

    return areFontsLoaded;
}
```
</details>


<details>
<summary>rncomp</summary>
  
- Create React Native functional component
```js
// rncomp: React Native Functional Component

import React from 'react';
import { View } from 'react-native';
import styles from './style';

export default function () {
    return (
        <View>
        </View>
    );
}
```
</details>


<details>
<summary>rnstyle</summary>
  
- Create React Native style
```js
// rnstyle: React Native Style

import { StyleSheet } from 'react-native';

const styles = StyleSheet.create({
    style: {
        
    },
});

export default styles;
```
</details>


<details>
<summary>rnscreen</summary>
  
- Create React Native screen
```js
// rnscreen: React Native Screen

import React from 'react';
import { StyleSheet, View } from 'react-native';

export default function ScreenFile({ navigation }) {
    return (
        <View style={styles.container}>
            
        </View>
    );
}

const styles = StyleSheet.create({
    container: {
        display: "flex",
        flex: 1,
        backgroundColor: "#f4f4f4",
    },
});
```
</details>


## ⬇️ Installation
### 🐧 Linux
1. Clone the repository
  ```shell
  git clone https://github.com/henriqueclaranhan/vscode-snippets.git
  ```
  
2. Copy the snippets to the VS Code snippets folder
  ```shell
  cp vscode-snippets/snippets/*.code-snippets ~/.config/Code/User/snippets/
  ```
  
- Optionally, you can delete the cloned repository folder
```shell
rm -rf vscode-snippets/
```
