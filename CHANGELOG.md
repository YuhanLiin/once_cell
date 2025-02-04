# Changelog

## 1.0.1

- fix unsoundness in `Lazy<T>` if the initializing function panics. Thanks [@xfix](https://github.com/xfix)!
- implement `RefUnwindSafe` for `Lazy`.
- share more code between `std` and `parking_lot` implementations.
- add F.A.Q section to the docs.

## 1.0.0

- remove `parking_lot` from the list of default features.
- add `std` default feature. Without `std`, only `unsync` module is supported.
- implement `Eq` for `OnceCell`.
- fix wrong `Sync` bound on `sync::Lazy`.
- run the whole test suite with miri.

## 0.2.7

- New implementation of `sync::OnceCell` if `parking_lot` feature is disabled.
  It now employs a hand-rolled variant of `std::sync::Once`.
- `sync::OnceCell::get_or_try_init` works without `parking_lot` as well!
- document the effects of `parking_lot` feature: same performance but smaller types.

## 0.2.6

- Updated `Lazy`'s `Deref` impl to requires only `FnOnce` instead of `Fn`

## 0.2.5

- `Lazy` requires only `FnOnce` instead of `Fn`

## 0.2.4

- nicer `fmt::Debug` implementation

## 0.2.3

- update `parking_lot` to `0.9.0`
- fix stacked borrows violation in `unsync::OnceCell::get`
- implement `Clone` for `sync::OnceCell<T> where T: Clone`

## 0.2.2

- add `OnceCell::into_inner` which consumes a cell and returns an option

## 0.2.1

- implement `sync::OnceCell::get_or_try_init` if `parking_lot` feature is enabled
- switch internal `unsafe` implementation of `sync::OnceCell` from `Once` to `Mutex`
- `sync::OnceCell::get_or_init` is twice as fast if cell is already initialized
- implement `std::panic::RefUnwindSafe` and `std::panic::UnwindSafe` for `OnceCell`
- better document behavior around panics

## 0.2.0

- MSRV is now 1.31.1
- `Lazy::new` and `OnceCell::new` are now const-fns
- `unsync_lazy` and `sync_lazy` macros are removed

## 0.1.8

- update crossbeam-utils to 0.6
- enable bors-ng

## 0.1.7

- cells implement `PartialEq` and `From`
- MSRV is down to 1.24.1
- update `parking_lot` to `0.7.1`

## 0.1.6

- `unsync::OnceCell<T>` is `Clone` if `T` is `Clone`.

## 0.1.5

- No changelog until this point :(
