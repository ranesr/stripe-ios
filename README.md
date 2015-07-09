# Stripe iOS SDK
[![Travis](https://img.shields.io/travis/stripe/stripe-ios/master.svg?style=flat)](https://travis-ci.org/stripe/stripe-ios)
[![CocoaPods](https://img.shields.io/cocoapods/v/Stripe.svg?style=flat)](http://cocoapods.org/?q=author%3Astripe%20name%3Astripe)
[![Carthage compatible](https://img.shields.io/badge/Carthage-compatible-4BC51D.svg?style=flat)](https://github.com/Carthage/Carthage)
[![CocoaPods](https://img.shields.io/cocoapods/l/Stripe.svg?style=flat)](https://github.com/stripe/stripe-ios/blob/master/LICENSE)
[![CocoaPods](https://img.shields.io/cocoapods/p/Stripe.svg?style=flat)](https://github.com/stripe/stripe-ios#)

This branch is WIP while iOS9 is in beta. Still to do:
- [ ] Confirm backwards compatibility with iOS7+
- [ ] Double-check new simulated `PKPayment` APIs with new Xcode betas
- [ ] Migrate NSURLConnection -> NSURLSession
- [ ] Add support for Contacts.framework
- [ ] Make sure CI works (this may have to wait until post-release)
- [ ] Fix other deprecations

The Stripe iOS SDK make it easy to collect your users' credit card details inside your iOS app. By creating [tokens](https://stripe.com/docs/api#tokens), Stripe handles the bulk of PCI compliance by preventing sensitive card data from hitting your server (for more, see [our article about PCI compliance](https://support.stripe.com/questions/do-i-need-to-be-pci-compliant-what-do-i-have-to-do)).

We also offer [seamless integration](https://stripe.com/applepay) with [Apple Pay](https://apple.com/apple-pay) that will allow you to securely collect payments from your customers in a way that prevents them from having to re-enter their credit card information.

## Requirements
Our SDK is compatible with iOS apps supporting iOS 6 and above. It requires Xcode 6.3+ and the iOS 8 SDK to build the source.

## Integration

We've written a [guide](https://stripe.com/docs/mobile/ios) that explains everything from installation, to creating payment tokens, to Apple Pay integration and more.

## Example apps

There are 2 example apps included in the repository:
- Stripe iOS Example (Simple) shows a minimal Swift integration with our iOS SDK.
- Stripe iOS Example (Custom) demonstrates 2 different ways of collecting your user's payment details: via Apple Pay, and STPPaymentCardTextField, a native credit card UI form component we provide. It also uses our [ApplePayStubs](https://github.com/stripe/ApplePayStubs) library to demonstrate how the Apple Pay flow appears in the iOS simulator (normally Apple Pay requires a device to use). It, too, uses a small example backend to make charges.

### Getting started with the Simple iOS Example App

Note: all the example apps require Xcode 6.4 to build and run.

Before you can run the app, you need to provide it with your Stripe publishable key.

1. If you haven't already, sign up for a [Stripe account](https://dashboard.stripe.com/register) (it takes seconds). Then go to https://dashboard.stripe.com/account/apikeys.
2. Replace the `stripePublishableKey` constant in ViewController.swift (for the Simple app) or Constants.m (for the Custom app) with your Test Publishable Key.
3. Head to https://github.com/stripe/example-ios-backend and click "Deploy to Heroku" (you may have to sign up for a Heroku account as part of this process). Provide your Stripe test secret key for the STRIPE_TEST_SECRET_KEY field under 'Env'. Click "Deploy for Free".
4. Replace the `backendChargeURLString` variable in the example iOS app with the app URL Heroku provides you with (e.g. "https://my-example-app.herokuapp.com")

After this is done, you can make test payments through the app (use credit card number 4242 4242 4242 4242, along with any cvc and any future expiration date) and then view them in your Stripe Dashboard!

## Running the tests

1. Open Stripe.xcworkspace
1. Choose the "iOS Tests" or "OS X Tests" scheme
1. Run Product -> Test

## Migrating from older versions

See `MIGRATING.md`
