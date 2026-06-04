# NexusBank - Bug Fixes and Card System Improvements

Please help me fix the following issues and improve the user experience across the NexusBank platform.

## Issue 1: Transactions & Cards Page Bug

### Problem

When a user clicks on the **Transactions** page or the **Cards** page, the user's email and username disappear from the interface.

### Expected Behavior

* The logged-in user's profile information should remain visible.
* Username and email should be loaded from Supabase and persist across all pages.
* User data should not reset when navigating between pages.
* Ensure proper state management and session handling.

---

## Issue 2: Transfer Money Form Improvements

### Current Problems

#### Recipient Name Auto-Fill

When a user enters a recipient's email address, the system should automatically display the associated username inside the:

**Recipient Name (Optional)**

field.

### Expected Behavior

1. User enters recipient email.
2. Search Supabase for a matching account.
3. If a user exists:

   * Automatically populate the Recipient Name field with their username.
   * Display a confirmation that the account was found.
4. If no account exists:

   * Show a clear error message.
   * Prevent transfers to invalid accounts.

---

#### Transfer Form Design Improvements

Current text:

"Search for a registered NexusBank user by email below, or enter their email manually."

The layout feels cluttered and confusing.

### Redesign Requirements

Create a cleaner transfer interface:

#### Recipient Information

* Recipient Email *

  * Search registered NexusBank users
  * Auto-detect existing accounts
  * Show account status

* Recipient Name

  * Auto-filled when user is found
  * Read-only field

* Transfer Amount *

* Transfer Note (Optional)

Use a modern banking-style design with:

* Better spacing
* Improved typography
* Clear field grouping
* Success and error states
* Mobile responsiveness

---

# NexusBank Card System

I would like to introduce a complete card management system that uses Supabase as the backend database.

## Features

### Add Existing Cards

Allow users to securely save their debit or credit cards.

Store:

* Card nickname
* Card type
* Last 4 digits
* Expiry date
* Card network (Visa, Mastercard, etc.)

Never store full card numbers or CVV values.

---

### NexusBank Virtual Cards

Allow users to create virtual NexusBank cards directly within the platform.

Features:

* Generate virtual card number
* Expiry date
* Cardholder name
* Card status (Active, Frozen, Expired)
* Spending limits
* Card locking/unlocking

---

### Database Structure (Supabase)

Create a Cards table:

cards

* id
* user_id
* card_name
* card_type
* card_network
* last_four_digits
* expiry_date
* status
* created_at

Create a Card Transactions table:

card_transactions

* id
* card_id
* amount
* merchant_name
* transaction_type
* transaction_date

---

### Card Dashboard

Create a dedicated Cards page showing:

* Active cards
* Virtual cards
* Card status
* Recent card transactions
* Freeze/Unfreeze card actions
* Create new virtual card button

---

## User Experience Improvements

The card section should feel similar to a modern digital banking application.

Suggested features:

* Beautiful card previews
* Real-time balance updates
* Transaction history
* Quick actions
* Dark mode support
* Mobile-friendly design

All card information, transfers, balances, and transactions must be synced with Supabase and update in real time.
