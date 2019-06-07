# The Altruistic Referral

Methods designed to work with the [altruistic referral](https://intercom.help/viral-loops/the-altruistic-referral-template/the-altruistic-referral-your-web-app) template.

---

## `identify_user()`
### `args`
  - `first_name`
  - `last_name`
  - `email`

### `kwargs`
  - `referral_code`: Referral code of the referring user
  - `referral_email`: Email address of the referring user
  - `referral_source`: Where the referral came from.
    - Can be any of `'email'|'facebook'|'twitter'|'redit'|'copy'`

---

## `track_conversion()`
### `args`
  - `email`: Email address of the user making a purchase

### Throws
  - `MissingReferrerException` when the user does not have a referrer

### Notes
Creates pending rewards in Viral Loops' system that you can then mark as
claimed.

---

## `get_pending_rewards()`
### `args`
  - `email`: Email address of the user you want rewards for
  - `referral_code`: Referral code of the user you want rewards for
  - `paginate`: Set to `True` to disable automatic fetching of further pages
  - `limit`: Used when `paginate` is `True`
  - `skip`: Used when `paginate` is `True`

### Notes
By default we fetch all relevant pending rewards, disregarding the pagination
rules. If this is causing problems with your API quota or memory, set
`paginate=True` in the `kwargs`.

---

## `redeem_reward()`
### `kwargs`
  - `reward_id`: ID of the reward you want to mark as redeemed
  - `email`: Email address of the user with rewards
  - `referral_code`: Referral code of the user with rewards

### Throws
  - `MissingFieldException` when no arguments are provided

### Notes
Only one of those arguments is required to make this method work.
If `reward_id` is given, only one reward is marked as redeemed.
If `email` or `referral_code` is given, all of that user's rewards
are marked as redeemed.
