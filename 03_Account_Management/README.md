# Account Management

## Overview

The Account Management module serves as a centralized hub for users to manage their post-purchase journey and personal preferences. It enables users to track orders, initiate returns, manage addresses and payment methods, access support, and update profile details.

The experience is designed to be self-service driven, reducing dependency on customer support while ensuring clarity, control, and transparency.

---

## 1. Navigation & Entry

### Overview

Users can access account-related functionalities through a dedicated profile section, typically via a dropdown or sidebar navigation. This acts as the entry point to all account features.

---

### Wireframe

![Account Navigation](side_navigation_myaccount.png)

---

### Features

- Centralized navigation for all account sections  
- Quick access to:
  - Orders  
  - Wishlist  
  - Addresses  
  - Payment Methods  
  - Profile  
  - Support  

---

### Logic

- Accessible only for logged-in users  
- Persistent navigation across account sections  
- Active section highlighted for clarity  

---

## 2. Order Management

### Overview

Allows users to view and manage all past and active orders, along with real-time status tracking and contextual actions.

---

### Wireframe

![Order History](order_history.png)

---

### Features

- View list of orders with key details  
- Status indicators:
  - Placed  
  - Packed  
  - Shipped  
  - Delivered  
  - Cancelled  
  - Payment Failed  
- Actions:
  - Cancel Order  
  - Retry Payment  
  - Reorder  
  - Return / Replace  

---

### Logic

- Cancel Order:
  - Available only before order is packed  
- Retry Payment:
  - Enabled for failed transactions  
- Return/Replace:
  - Enabled only after delivery  
- Status-based UI rendering  

---

## 3. Returns & Replacement

### Overview

Enables users to initiate return or replacement requests through a structured and validated flow.

---

### Wireframe

![Return Replace](return_replace.png)  
![Return Confirmation](return_confirmation.png)  
![Return Validation](return_validation_message.png)

---

### Features

- Reason selection (mandatory)  
- Optional comments  
- Image/video upload (mandatory where applicable)  
- Return or Replace selection  
- Confirmation before submission  

---

### Logic

- Submission blocked without reason  
- Upload required for certain categories  
- Request moves to “Under Review” state  
- SLA: 24–48 hours for validation  
- Status updated post approval/rejection  

---

## 4. Address Management

### Overview

Allows users to manage delivery addresses for faster and more accurate checkout experiences.

---

### Wireframe

![Addresses](my_addressess.png)

---

### Features

- Add new address  
- Edit existing address  
- Delete address  
- Set default address  

---

### Logic

- Default address used during checkout  
- Address validation based on serviceability (pincode)  
- At least one valid address required for order placement  

---

## 5. Payment Methods

### Overview

Users can manage saved payment methods to enable faster and secure transactions.

---

### Wireframe

![Payment Methods](my_payment_methods.png)

---

### Features

- View saved cards  
- Add new card  
- Delete card  
- Mark default payment method  

---

### Logic

- Expired cards cannot be used  
- Secure storage of payment details (masked)  
- Default payment method prioritized during checkout  

---

## 6. Wishlist

### Overview

Allows users to save products for future consideration and quick access.

---

### Wireframe

![Wishlist](wishlist.png)

---

### Features

- View saved items  
- Add to cart  
- Remove from wishlist  

---

### Logic

- Wishlist persists for logged-in users  
- Items can be moved directly to cart  
- Reflects real-time product availability  

---

## 7. Personal Information

### Overview

Users can view and update their personal profile details.

---

### Wireframe

![Personal Info](personal_info.png)

---

### Features

- Edit name, phone, email  
- Update address details  
- Save profile changes  

---

### Logic

- Validation for email and phone format  
- Changes reflected across system (orders, checkout)  

---

## 8. Customer Support

### Overview

Provides users with assistance through chat and self-service help options.

---

### Wireframe

![Support](customer_support.png)  
![FAQ](faq.png)

---

### Features

- Chat interface with support  
- Quick action queries  
- FAQ access  
- Media upload for issue reporting  

---

### Logic

- Order-linked queries prioritized  
- Chat escalation to agent when required  
- FAQs reduce dependency on live support  

---

## Error Handling & Edge Cases

### Overview

Handles failures and exceptions across account functionalities to ensure a smooth and reliable user experience.

---

### Scenarios

- Cancel option hidden after order is packed  
- Return submission blocked without required inputs  
- Expired cards disabled for selection  
- Invalid address updates rejected  
- Payment retry available for failed orders  
- Support unavailable fallback (FAQ / retry)  

---

### Product Thinking

- Contextual actions reduce user confusion  
- State-based controls prevent invalid operations  
- Self-service flows reduce support dependency  
- Clear feedback improves trust and usability  
