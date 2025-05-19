# 📘 UIHelper Class Documentation

A utility class that centralises UI logic, platform checks, and widget building helpers used across the Flutter app.

---

## 🔍 Platform & Device Detection

### `Future<void> detectSimulator()`
Detects if the app is running on a simulator/emulator, and whether it's an iOS or Android device.

- Sets internal flags `_isSimulator`, `_isIOS`, and `_isAndroid`.
- Must be called before using other device-dependent methods like `getFontSize()`.

---

### `double getFontSize(...)`
Returns a font size based on platform and whether it is a simulator or a real device.

**Parameters**:
- `simulatorIOSSize`, `simulatorAndroidSize`
- `deviceIOSSize`, `deviceAndroidSize`

**Returns**: A `double` representing the font size based on detected environment.

---

### `Future<String> sizeByDeviceModel()`
Returns the model size hint or name for iOS devices, used for responsive scaling logic.

**Returns**: A string representing the device model or `"1.2"` by default for Android.

---

### `Future<double> getDynamicSizedBoxHeight()`
Returns a dynamic height for spacing based on iOS version.

**Returns**: `60` for iOS devices, `16` for others.

---

### `Widget buildDynamicSizedBox({required AsyncSnapshot<double> snapshot})`
Builds a `SizedBox` with height based on a future-driven snapshot.

---

## 🧱 UI Component Builders

### `Widget buildTextField(...)`
Builds a standard styled `TextField`.

**Key Parameters**:
- `label`: Field label
- `hint`: Hint text
- `icon`: Optional prefix icon
- `onChanged`, `onSubmitted`
- `minLength`, `inputFormatters`
- `suffixIcon`, `controller`

**Returns**: A styled `TextField` wrapped in a `Padding`.

---

### `Widget buildTextArea(...)`
Builds a styled multi-line text area using `TextAreaWidget`.

**Key Parameters**:
- `label`, `hint`, `controller`, `onChanged`
- `maxLines`, `minLines`, `minLength`, `maxLength`
- `obscureText`, `textAlign`, `fontWeight`, `fontSize`

**Returns**: A `TextAreaWidget`.

---

### `Widget buildDropdown(...)`
Builds a `DropdownButtonFormField` with preset styling and label.

**Parameters**:
- `context`: BuildContext for styling
- `label`: Label of dropdown
- `options`: List of values
- `selectedValue`: Current value
- `onChanged`: Callback on selection

---

### `Widget buildText(...)`
Custom text builder with optional style injection.

**Parameters**:
- `text`: The text content
- `style`: Optional external style function
- `maxLines`, `textAlign`, `color`, `weight`

**Returns**: A `Text` widget with styling defaults based on platform.

---

## 🎨 Input Borders

### `_defaultInputBorder()`, `_enabledInputBorder()`, `_focusedInputBorder()`
Returns preconfigured `OutlineInputBorder` styles with different use-cases:
- Default (no side)
- Enabled (light grey)
- Focused (black)

---

### `OutlineInputBorder buildInputBorder(Color color)`
Generic border builder with custom color and radius 12.

---

## 🎨 Constants

Colour constants used throughout UI:
- `backgroundColor`, `primaryColor`, `secondaryColor`, `accentColor`
- `successColor`, `infoColor`, `blackBlueColor`, `black37BlueColor`

---

## ✅ Internal State

- `_isSimulator`: Whether running on a simulator/emulator
- `_isAndroid`, `_isIOS`: Platform flags, set during `detectSimulator()`

---

## ⚠️ Usage Notes

- **Important**: Call `await UIHelper.detectSimulator()` early in your app (e.g. in `main()`) to ensure environment detection works properly.
- `getFontSize()` and similar methods rely on these flags being set.

