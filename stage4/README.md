## Unit Tests

Run from the project root:

```bash
PYTHONPATH=Backend python manage.py test users
```

| Function | Tests |
|---|---|
| `login` | Successful login, wrong password |
| `register` | Successful registration, duplicate email |
| `logout` | Successful logout, missing refresh token |
| `get_my_profile` | Fetching the user's profile |
| `update_profile` | Awards 20 points when the profile becomes complete |
| `add_points` | Known event, unknown event |

### Test code

#### 1. Helpers and authentication tests

![Auth tests]
<img width="1106" height="1092" alt="١" src="https://github.com/user-attachments/assets/967c06d0-680c-4e2e-8f3a-4376bd4cad5c" />


This part contains two helper functions and the authentication tests:
- `valid_skill_level()` reads a valid value for `skill_level` from the `Profile` model, so the tests don't depend on a hardcoded value.
- `post()` builds a JSON request and optionally authenticates it as a given user.
- `AuthTests` covers `login`, `register`, and `logout`, including success cases and error cases (wrong password, duplicate email).

#### 2. Profile and points tests

![Profile and points tests]
<img width="1077" height="1120" alt="٢" src="https://github.com/user-attachments/assets/72543f99-04f6-4aed-b027-6c9d95660740" />


This part covers the logout error case, the profile, and the points system:
- `test_logout_missing_token` checks that logout returns `400` when no refresh token is sent.
- `ProfileTests` checks that the profile is returned and that completing it (bio and skill level) awards 20 points.
- `AddPointsTests` checks that `match_win` gives 50 points and that an unknown event gives 0.
## Project Links

| Item | Link |
|---|---|
| Sprint Reviews | [link](https://) |
| Retrospectives | [link](https://) |
| Sprint Planning | [link](https://) |
| Source Repository | [link](https://github.com/ORG/REPO) |
| Bug Tracking | [link](https://) |
| Testing Evidence and Results | [link](#unit-tests) |
| Production Environment | [link](https://) |

### Notes

- **Sprint Reviews / Retrospectives / Sprint Planning:** link to the Notion, Google Docs, or Miro pages where they are documented.
- **Bug Tracking:** link to GitHub Issues, Jira, or Trello.
- **Testing Evidence and Results:** points to the Unit Tests section in this README, which includes the test code screenshots and the run command.
- **Production Environment:** link to the live deployment (for example Render, Railway, or Vercel).
