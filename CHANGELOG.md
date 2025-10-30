# Change log

## main

- Do not call `#subscribed` when subscription is rejected in a `before_subscribe` callback.

## 0.2.0

- Performance: store connections in a Hash, not an Array.

- Add `Connection#broadcast` as an interface for broadcasting from channels.

- Add `config.fastlane_broadcasts_enabled` to opt-in for optimized broadcasts (no double JSON encoding).

## 0.1.2

- Added a hack to prevent third-party extensions from changing the methods visibility.

## 0.1.1

- Added RSpec patch.

## 0.1.0

- Initial extraction.
