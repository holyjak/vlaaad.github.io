---
layout: reveal
title: "Reveal Pro:<br>Read Eval Visualize Loop for&nbsp;Clojure, Supercharged"
permalink: /reveal-pro
---

![Demo](/assets/reveal-pro/main.gif)

| [![Clojars Project](https://img.shields.io/clojars/v/dev.vlaaad/reveal-pro.svg?logo=clojure&logoColor=white&style=for-the-badge)](https://clojars.org/dev.vlaaad/reveal-pro) | [![Slack Channel](https://img.shields.io/badge/slack-%20%23reveal-blue.svg?logo=slack&style=for-the-badge)](https://clojurians.slack.com/messages/reveal/) |

* auto-gen table of contents
{:toc}

# What is Reveal Pro

Reveal Pro is an improved version of [Reveal](/reveal/) that aims to be batteries included so you can focus on your problems with data and knowledge you need, available as soon as you need it. 

It is a fork of Reveal that should be used instead of Reveal, not alongside it.

Reveal Pro costs $9.99 per month — [start a free trial](https://buy.stripe.com/8wM9Dz5bKand5ck3cc){: .buy-button}!

# Getting started

Here are the steps needed to start using Reveal Pro:

1. Add a dependency on Reveal Pro, e.g.

   ```sh
   $ clj \
     -Sdeps '{:deps {dev.vlaaad/reveal-pro {:mvn/version "1.3.248"}}}' \
     -X vlaaad.reveal/repl
   ```

2. [Start a free trial here](https://buy.stripe.com/8wM9Dz5bKand5ck3cc){: .buy-button}.

3. Once you start a trial, you'll receive an email with the Reveal Pro license key — paste it into a license input field in the Reveal Pro window. 

You are good to go!

# Configuration

Everything the applies to Reveal also applies to Reveal Pro (sans the dependency coordinate), see [Reveal docs](/reveal/) for all available configuration options and instructions.

# Unique features

## Forms

Forms allow you to convert data structure specifications to UI input components for creating these data structures. This is a generic and multi-purpose tool that supports Clojure spec out of the box and can be extended to other data specification libraries.

What leverage can it give you?

1. Learn possible shapes of expected data.

   Specs describe the data shape, but looking at the spec is not the easiest way to understand what are the possible shapes for the specified data. Do you remember all the clauses `ns` form supports? Where to look for available `:gen-class` options? With Forms, you can learn all that simply starting from the `clojure.core/ns` symbol:

   ![ns form demo](/assets/reveal-pro/ns-form.gif)

2. Explore data-driven APIs

   Form state is a ref that can be observed — you can watch it and create derived views that refresh on form changes:

   ![explore form demo](/assets/reveal-pro/explore.gif)

3. Create data structures with contextual help

   Forms provide contextual actions and information on selectable parts of data structures that you can activate by pressing <kbd>F1</kbd> or <kbd>Ctrl Space</kbd>. For example, with spec forms, you can use fine-grained generators to generate parts of the data structures. You can also copy and paste these data structures as text:

   ![contextual help demo](/assets/reveal-pro/create.gif)

Forms are available either with:
- `form:spec` contextual action on Clojure specs;
- `vlaaad.reveal.pro.form` ns that allows creating fine grained forms as well as reactive views that update on form state changes, e.g.:
  ```clj
  (require '[vlaaad.reveal.pro.form :as form]
           '[clojure.spec.alpha :as s])

  {:fx/type form/form-view
   :form (form/spec-alpha-form `ns)}
  ```
  After evaluating this map, you can select `view` action on it in Reveal Pro window to see the form. Tip: see [Interacting with Reveal from code](/reveal/#interacting-with-reveal-from-code) to be able to immediately open the form without having to interact with Reveal window.

## File system navigation

Reveal Pro adds support for Java's file system APIs that allow navigating folders and zip/jar archives. Explore your classpath:

![fs demo](/assets/reveal-pro/fs.gif)

## ...And more are on the way

More tools are being developed for Reveal Pro that aim to solve common development problems. Particularly, database exploration is one area that I intend to improve in the future.

You can stay up to date and talk to me or other Reveal users in [#reveal](https://clojurians.slack.com/messages/reveal/) channel of Clojurians slack.

# Subscription management and cancellation

When you start a trial and receive a license key, you'll also get a subscription management link where you'll be able to change the payment method or cancel the subscription. You can also write to [reveal@vlaaad.dev](mailto:reveal@vlaaad.dev) to request cancellation.

After your trial period, you will automatically be billed monthly. You may cancel your subscription at any time. You are responsible for the full subscription fee in the monthly billing cycle in which you cancel. Once your account has been billed, all sales are final and there will be no refunds. You'll be able to continue using Reveal Pro after cancellation until the end of the billing cycle.

See also: [terms of service](/reveal-pro/terms) and [privacy policy](/reveal-pro/privacy).
