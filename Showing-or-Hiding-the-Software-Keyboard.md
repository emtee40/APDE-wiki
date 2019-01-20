## AKA "How do I show/hide the soft keyboard?"

Android mode includes built-in functionality for opening and closing the software keyboard. See the [reference](https://android.processing.org/reference/keyboard/virtual.html).

```processing
// To open the keyboard:
openKeyboard();
// To close the keyboard:
closeKeyboard();
```

### Pre-Android Mode 4.0

> Note: This approach is no longer necessary in new versions of APDE.

Showing and hiding the software keyboard requires using a little bit of native Android functionality.

First, you'll need an InputMethodManager:

```processing
android.view.inputmethod.InputMethodManager imm = (android.view.inputmethod.InputMethodManager) getActivity().getSystemService(android.content.Context.INPUT_METHOD_SERVICE);
```

Then to show, hide, or toggle the soft keyboard, use the following three methods:

```processing
// Show
imm.showSoftInput(getActivity().getCurrentFocus(), 0);

//Hide
imm.hideSoftInputFromWindow(getActivity().getCurrentFocus().getWindowToken(), 0);

// Toggle
imm.toggleSoftInput(0, 0);
```

You can copy and paste the functions below into your sketch to abstract away this process:

```processing
void toggleSoftKeyboard() {
  android.view.inputmethod.InputMethodManager imm = (android.view.inputmethod.InputMethodManager) getActivity().getSystemService(android.content.Context.INPUT_METHOD_SERVICE);
  imm.toggleSoftInput(0, 0);
}

void showSoftKeyboard() {
  android.view.inputmethod.InputMethodManager imm = (android.view.inputmethod.InputMethodManager) getActivity().getSystemService(android.content.Context.INPUT_METHOD_SERVICE);
  imm.showSoftInput(getActivity().getCurrentFocus(), 0);
}

void hideSoftKeyboard() {
  android.view.inputmethod.InputMethodManager imm = (android.view.inputmethod.InputMethodManager) getActivity().getSystemService(android.content.Context.INPUT_METHOD_SERVICE);
  imm.hideSoftInputFromWindow(getActivity().getCurrentFocus().getWindowToken(), 0);
}
```

### Ketai

If you are using the Ketai library, then you may instead choose to use [KetaiKeyboard](http://ketai.org/reference/ui/ketaikeyboard/) for showing, hiding, and toggling the keyboard.