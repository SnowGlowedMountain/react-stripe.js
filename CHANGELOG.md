# Changelog

React Stripe.js adheres to
[Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## v7.0.0-beta.0 2019-12-18

- No code changes from the last alpha release
- Add official docs
- Add a migration guide
- Update Readme

## v7.0.0-alpha.5 2019-12-17

- Fix a vulnerability in a build dependency
- Code quality

## v7.0.0-alpha.4 2019-12-06

### New Features

- Add support for passing an Element component to `elements.getElement`

```js
const cardElement = elements.getElement(CardElement);
```

- Add a new hook, `useStripe` which returns the Stripe object passed to
  `<Elements>`

```js
const stripe = useStripe();
```

- Expand `<ElementsConsumer>` to provide both the Elements and Stripe objects.

```jsx
<ElementsConsumer>
  {({stripe, elements}) => (
    <MyCheckoutForm stripe={stripe} elements={elements} />
  )}
</ElementsConsumer>
```

### Breaking Changes

- Passing `undefined` to the `stripe` prop of `<Elements>` is no longer
  possible. If you are async loading Stripe.js, you will need to explicitly pass
  `null`.
- The value provided by `<ElementsConsumer>` has changed to support providing
  Stripe as well as Elements.

## v7.0.0-alpha.3 - 2019-11-15

Fix minified UMD build

## v7.0.0-alpha.2 - 2019-11-15

Fix dependencies

## v7.0.0-alpha.1 - 2019-11-15

### Breaking Changes

- Drop injectElements since it is easy to implement with `ElementsConsumer` if
  users want to use the HOC pattern.

### Fixes

- Better errors when trying to call `useElements` or mount components that rely
  on Elements context outside of an provider.
- Test cleanup

## v7.0.0-alpha.0 - 2019-11-05

Initial alpha release

---

For changes to versions before v7.0.0 please refer to the
`react-stripe-elements`
[changelog](https://github.com/stripe/react-stripe-elements/blob/master/CHANGELOG.md).
