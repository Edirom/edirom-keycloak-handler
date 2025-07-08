# Keycloak Web Component Handler

This repository provides a reusable Web Component for Keycloak authentication in vanilla JavaScript applications.

## Features

- Custom element `<keycloak-login>` for easy Keycloak integration
- Loads Keycloak JS as an ES6 module (must be present in `/vendor/keycloak@26.2.0/lib/keycloak.js`)
- Handles SSO, login, and token storage as a cookie
- Works in any modern browser and can be embedded in other apps

## Usage

1. **Add the Web Component to your HTML:**

   ```html
   <keycloak-login
     url="https://keycloak.yourDomain.de"
     realm="your-realm"
     client-id="your-client-id">
   </keycloak-login>
   <script type="module" src="./keycloak-handler.js"></script>
   ```

2. **Required attributes:**
   - `url`: The Keycloak server URL (e.g. `https://keycloak.yourDomain.de`)
   - `realm`: The Keycloak realm name (e.g. `your-realm`)
   - `client-id`: The Keycloak client ID (e.g. `your-client-id`)

3. **Keycloak JS dependency:**
   - You must provide the Keycloak JS adapter as an ES6 module at `/vendor/keycloak@26.2.0/lib/keycloak.js` (with `export default ...`).
   - Download from the official Keycloak release or build it as ESM if needed.

4. **Configuration:**
   - Make sure your Keycloak client is configured for CORS and has the correct redirect URIs.
   - The component will store the token as a cookie after successful login.

## Example

See `index.html` for a minimal working example.

## License

See LICENSE.txt or your organization's policy.
