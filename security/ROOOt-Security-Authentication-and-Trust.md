# ROOOt Security, Authentication & Trust Specification (Draft v1)

> **Purpose:** Protect humans first, especially the most vulnerable.
>  
> **Design rule:** Security must scale downward (poorest, least connected, most at risk) before it scales upward.

---

## 1. Core Security Principles

1. **Biometrics are convenience, not authority**
2. **No single factor can unlock everything**
3. **Loss must be bounded**
4. **Duress must be survivable**
5. **Exit is always allowed**

ROOOt optimizes for dignity under pressure, not perfect cryptography.

---

## 2. Wallet Architecture (Mandatory)

ROOOt uses a **multi-wallet model**.

### 2.1 Pocket Wallet (Daily Use)
- Purpose: food, transport, small exchanges
- Balance limit: intentionally low
- Unlock options:
  - PIN
  - biometric (optional, device-local)
- Instant transfers allowed
- Treated as cash-in-pocket

Loss is acceptable but limited.

---

### 2.2 Vault Wallet (Core Balance)
- Purpose: savings and long-term stewardship
- Unlock requires **2 of 3**:
  - passphrase
  - time delay (24–72 hours)
  - guardian approval
- No instant large transfers
- Biometrics alone are **never sufficient**

The vault protects against panic, coercion, and mistakes.

---

### 2.3 Duress / Decoy Wallet (Strongly Recommended)
- Opens under alternate unlock pattern
- Shows believable but limited balance
- Allows small transfer
- Cannot access vault
- Appears normal to an attacker

This makes violent coercion inefficient.

---

## 3. Biometrics Policy

- Biometrics may **unlock keys**, never *be* keys
- All biometric processing is device-local
- No biometric data leaves the device
- Every biometric action has a non-biometric fallback

**Reason:** faces and fingerprints cannot be rotated; keys can.

---

## 4. Spend Controls & Theft Resistance

- Daily spend limits on pocket wallets
- Velocity limits on transfers
- Large transfers require delays or guardians
- Offline instruments (paper, NFC) must have:
  - strict maximum value
  - expiry
  - redemption verification

Goal: theft never becomes catastrophic.

---

## 5. Social Recovery (No Central Authority)

- Users nominate 3–5 guardians
- Any threshold (e.g. 3 of 5) can restore access
- Guardians cannot move funds
- Guardians cannot change ownership

This replaces passwords-as-death.

---

## 6. Identity & Access Tiers

ROOOt avoids global identity choke points.

- **Tier 0:** anonymous, local, survival-level access
- **Tier 1:** community-verified participation
- **Tier 2:** strong proof-of-personhood for portability and cap-level use

No tier blocks survival.

---

## 7. Builder Trust & Anti-Troll Measures

- Anyone may build
- No one is automatically canonical
- Reference implementations must:
  - obey protocol invariants
  - have no hidden privilege layers
  - survive hostile review
- AI may assist pattern detection
- Humans make final trust decisions

Trust is earned, never purchased.

---

## 8. State & Power Threat Model

Assumed threats:
- forced KYC
- biometric seizure
- wallet confiscation
- legal bans
- surveillance mandates

ROOOt must survive **partial compliance and partial resistance**.

---

## 9. Defensive Design Responses

- No central kill switch
- No admin keys
- Multiple implementations
- Local-first verification
- Forkability as escape

Capture creates fragmentation, not control.

---

## 10. Final Security Invariant

> **ROOOt protects people, not assets.**

If forced to choose:
- human safety > system purity
- survivability > efficiency
- dignity > compliance

Any implementation violating this is **not ROOOt**.
