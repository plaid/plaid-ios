# Plaid Integration Migration Guide: LinkKit 4.x to 5.x

This document provides a comprehensive guide on upgrading your Plaid integration from LinkKit 4.x to 5.x. It outlines the necessary steps and important changes to ensure a smooth transition.


## Overview

The upgrade from LinkKit 4.x to 5.x introduces a few breaking changes that you should be aware of. This guide outlines these changes to facilitate a seamless migration process.

### Changes from SDK 4.x to 5.0

#### 1. iOS Version Support
**BREAKING**: Dropped support for iOS 11, 12, & 13.

If your application still supports iOS 11, 12, or 13, you must either continue using SDK 4.x or update your app to support newer iOS versions compatible with SDK 5.x.

#### 2. Authentication Method Changes
**BREAKING**: Removed deprecated support for public key authentication.

If your integration is using public key authentication, it's essential to migrate to Link Tokens. This change does not affect you if you've already made this transition. For detailed instructions, refer to Plaid's [migration guide](https://plaid.com/docs/link-token-migration-guide).

#### 3. OAuth Redirect Handling
**BREAKING**: Removed deprecated `continue(from:)` method (no longer required for OAuth redirects).

If your code calls the deprecated `continue(from:)` method for OAuth redirects, you can safely remove this call. It is no longer needed.

#### 4. Open Options Configuration
**BREAKING**: Removed deprecated OpenOptions parameter from `func open(presentUsing method: PresentationMethod, _ options: OpenOptions)`

If your integration relies on `OpenOptions`, you must now configure these parameters while creating your [Link Tokens](https://plaid.com/docs/api/tokens/). Update your implementation accordingly.

### Review your codebase

It's crucial to review your existing codebase and make the necessary adjustments to accommodate these changes. Failure to do so might result in integration issues and a suboptimal user experience.

By following these guidelines, you can successfully migrate your Plaid integration from LinkKit 4.x to 5.x, ensuring compatibility with the latest features and security enhancements.

For any additional support or queries, feel free to reach out to Plaid's [Support Team](https://dashboard.plaid.com/support/new).