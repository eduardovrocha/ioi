# CoinCounterActionComponent

## Overview

`CoinCounterActionComponent` is a `StatefulWidget` in Flutter responsible for handling a "tip" action where users can send a coin to a piece of content. It provides animated feedback including scaling effects, coin splash animation, and balance updates.

---

## Props

- **content** (`Map<String, dynamic>`) - Required: The content data, including `id` and settings like `tip_owner`.
- **hasTipped** (`bool`) - Required: Indicates if the user has already tipped this content.
- **onSuccess** (`void Function()?`) - Optional: Callback executed after a successful tip.

---

## State Variables

- `_coinCount` (`double`) - Current number of tips for the content.
- `_contentId` (`int`) - Content ID.
- `_showTooltip` (`bool`) - Controls visibility of splash animation.
- `_hasTipped` (`bool`) - Tracks if the user has tipped (initial value based on widget's `hasTipped`).
- `_isPressed` (`bool`) - Indicates if the button is being pressed.
- `_isSending` (`bool`) - Prevents multiple requests when holding down.
- `_pressStartTime` (`DateTime`) - Time when button press started.
- `_tooltipController` (`AnimationController`) - Manages tooltip (coin splash) animation.
- `_pressController` (`AnimationController`) - Manages button press scaling effect.

---

## Animations

- **SlideTransition** - Coins move outward in three directions: left-up, straight-up, right-up.
- **FadeTransition** - Coins fade out while flying.
- **ScaleTransition** - Button scales up on press.

---

## Lifecycle

- **initState**
    - Initializes providers, controllers, animations.
- **dispose**
    - Disposes animation controllers.

---

## Key Methods

- **updateBalance(double newBalance)**
    - Updates the user's wallet balance in the provider and notifies listeners.

- **_incrementCoin()**
    - Increments coin count visually.
    - Calls `postTipOwner` on `ContentProvider`.
    - On success, updates entrance balance and triggers success callback.

- **_sendCoinRequest()**
    - Triggers device vibration on tip action.

- **_onTapDown(TapDownDetails details)**
    - Starts scale animation and calls `_incrementCoin` and `_sendCoinRequest` if holding down.

- **_onTapUp(TapUpDetails details)** and **_onTapCancel()**
    - Resets scale animation.

- **_buildSplashCoins()**
    - Generates multiple flying coin widgets using `SlideTransition` and `FadeTransition`.

---

## UI Structure

- **GestureDetector** wraps the main interaction container.
- **Container** holds the animated coin counter and a coin image.
- **Stack** structure allows overlaying flying coins.

---

## Assets

- **Coin Image**: `assets/images/theme/default-icon/coin.png`

---

## Dependencies

- `provider` for accessing providers (`EntranceProvider`, `ContentProvider`).
- `vibration` package to handle device vibration feedback.

---

## Notes

- Safe access to nested maps (e.g., `widget.content['settings']?['tip_owner']`).
- Good control to avoid multiple submissions using `_isSending` flag.
- Mounted check after animations.
- Graceful fallback if vibration API fails.

---

## Potential Improvements

- Abstract splash coins directions and properties for easier reuse.
- Move hardcoded image paths and animation durations into constants.
- Add visual feedback for failure cases (e.g., API request fails).
- Allow vibration feedback to be optional based on user settings.
