# UseCaseRef

**UseCaseRef** is a simple and structured system for documenting use cases in app development. It helps developers and testers track user flows, actions, and outcomes in a modular and reference-based way, making the process of defining, testing, and managing complex app scenarios easier.

## Table of Contents
- [What is UseCaseRef?](#what-is-usecaseref)
- [Why UseCaseRef?](#why-usecaseref)
- [How It Works](#how-it-works)
- [UseCaseRef Structure](#usecaseref-structure)
- [Example](#example)
- [Getting Started](#getting-started)
- [Contributing](#contributing)
- [License](#license)

## What is UseCaseRef?

**UseCaseRef** is a documentation framework designed for app developers and testers to organize use cases in a clear and scalable manner. Whether it's for mobile, web, or desktop apps, **UseCaseRef** lets you define user actions, roles, and processes using references and structured steps. This makes it easy to handle complex user flows, error handling, and testing scenarios.

## Why UseCaseRef?

In modern app development, use cases can become complex, especially with multiple user actions, options, and dependencies. **UseCaseRef** helps solve these challenges by:
- Creating a clear, modular system for tracking user actions and flows.
- Making it easier to link use cases together using references (`ref`).
- Simplifying communication between developers, designers, and testers.
- Streamlining both positive and negative (failed) scenarios.

## How It Works

UseCaseRef structures user flows using a combination of:
- **ref**: A unique identifier for each action step.
- **action**: A description of the user's action (e.g., signup, login).
- **role**: The role of the user at that point (e.g., visitor, user).
- **pre-process**: Defines any preceding steps that need to happen before the action.
- **process**: A step-by-step breakdown of what happens during the action, including success and failure outcomes.

## UseCaseRef Structure

Here is the basic structure of a **UseCaseRef**:

```
ref: Unique reference ID
action: What the user is doing (e.g., signup, login)
role: The user's role (e.g., visitor, user)
pre-process: Previous reference that must occur before this action (optional)
process:
    CLICK {buttonName}(page)
    OPTIONS[{option1:to(ref-X), option2:to(ref-Y)}](next-page)
    OK: {success-path}
    FAILED: {failure-path}
```

### Fields:
- **ref**: Unique identifier for each use case step.
- **action**: Describes the specific user action (e.g., login, sign up).
- **role**: Identifies the role the user has in the system during that action (visitor, user, admin, etc.).
- **pre-process**: Lists previous steps that must occur before this action.
- **process**: Outlines the steps for executing the action, including options and outcomes (success or failure).

## Example

Here’s an example of how a signup flow might be documented in **UseCaseRef**:

```
ref: 001
action: install app and signup as new user
role: visitor
process:
    CLICK appIcon
    CLICK nextBtn(page-intro)
    OPTIONS[signupWithGoogleBtn:to(ref-003), signupWithFacebookBtn:to(ref-003), signupWithEmailBtn:to(ref-004), iAlreadyHaveAnAccountBtn:to(page-login)](page-signup)

ref: 003
action: signup with google or facebook
role: visitor
pre-process: ref-001
process:
    CLICK signupWithGoogleBtn(page-signup)
    OK: to(page-choose)
    FAILED: to(page-choose)
```

## Getting Started

### 1. Clone the Repository
To start using **UseCaseRef** in your project, clone the repository:

```bash
git clone https://github.com/emekaobianom/useCaseRef.git
```

### 2. Documentation
Use the provided templates and guidelines in the repository to start documenting your app's use cases. The `templates/` folder contains example `.md` files to guide you through documenting user flows.

### 3. Customization
You can modify the structure to fit your specific app needs or extend it for additional roles, conditions, or processes.

## Contributing

We welcome contributions from the community to improve **UseCaseRef**. Here's how you can help:
1. **Fork the repository**.
2. **Create a new branch** for your feature or bugfix.
3. **Submit a pull request**.

Feel free to open issues for suggestions, bugs, or general feedback.

## License

**UseCaseRef** is released under the MIT License. See the [LICENSE](LICENSE) file for more details.

