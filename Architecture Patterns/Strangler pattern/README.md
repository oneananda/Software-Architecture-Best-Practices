# Strangler pattern - General Overview

The Strangler pattern is a technique used to gradually migrate an application to a different architecture.

This is like upgrading your home while still living in it—room by room, instead of tearing the whole house down and rebuilding it from scratch. It allows you to gradually replace an old, outdated system with a shiny new one without stopping your business operations. This approach is less risky, more manageable, and ensures you keep things running smoothly.

The name "Strangler Pattern" comes from the natural phenomenon of a "strangler vine" or "strangler fig," which is a type of plant that grows around a tree. Over time, the vine gradually envelops the tree, eventually replacing it entirely, but without immediately killing the tree. The tree continues to function as the vine slowly takes over its structure.

## When to Use the Strangler Pattern

- **Gradual Modernization:** Your current system is old but can't just be shut down for a complete overhaul.
- **Reducing Risks:** You want to test new features step-by-step, without betting everything on one big switch.
- **No Downtime:** Critical business operations need to keep running during the upgrade.
- **Parallel Development:** You want to develop the new system alongside the old one.

## How the Strangler Pattern Works

Imagine you have an old tree (your legacy system), and you want to replace it with a new vine (your new system). The vine grows over the tree slowly, eventually taking over its functions without killing the tree immediately.

### Steps to Implement the Strangler Pattern

1. **Identify What to Replace First:**
   - Look for the oldest, most troublesome parts of your system—those are the "rooms" to renovate first.
   - **Example:** You have an old user authentication module that’s slow and hard to maintain.

2. **Build the New Component:**
   - Create a new, improved version of that component using modern technology.
   - **Example:** Build a new user authentication service using microservices and OAuth.

3. **Set Up a Facade or Proxy:**
   - Use a proxy (like an API Gateway) to decide whether to send requests to the old or new component.
   - **Example:** The API Gateway checks if a user request should be handled by the old authentication system or the new one.

4. **Gradually Migrate Functions:**
   - Slowly switch parts of the system to the new component as it gets ready.
   - **Example:** Start with new users using the new authentication service while existing users still use the old one.

5. **Test and Monitor:**
   - Make sure the new component is working as expected by running it in parallel with the old one.
   - **Example:** Track login failures, performance issues, and user feedback to ensure the new system is performing well.

6. **Switch Over Completely:**
   - Once confident, route all traffic to the new component and stop using the old one.
   - **Example:** After a few months, all users now authenticate using the new service, and the old one is decommissioned.

7. **Retire the Old System:**
   - After everything works fine, fully shut down the legacy component.
   - **Example:** Completely remove the old authentication codebase and clean up related resources.

8. **Keep Improving:**
   - Continue upgrading other parts of your system using the same steps.
   - **Example:** Next, tackle the payment processing module with the same Strangler approach.

## Example Scenario

### Old System

You have a monolithic e-commerce application with an outdated payment module. It’s hard to maintain, slow, and occasionally fails during high traffic.

### Applying the Strangler Pattern

1. **Identify and Plan:** The payment module is identified as a critical but troublesome part.
2. **Build New:** Develop a new payment microservice with modern technologies (like Node.js, using Stripe API).
3. **Set Up Proxy:** Implement an API Gateway to route payment requests based on a flag or user type.
4. **Migrate Gradually:** Start directing payments for new orders through the new microservice.
5. **Test and Monitor:** Use metrics and logs to compare performance between the old and new systems.
6. **Switch Over:** Once stable, move all or sizable traffic called [Canary Release](#canary-release) to the new payment microservice.
7. **Retire the Old Module:** Decommission the old payment code.
8. **Iterate:** Continue with other parts of the monolith, like inventory management or user profiles.

### Canary Release / Canary Deployment

This approach involves deploying new features or versions to a small, controlled subset of users or traffic first.

The term "canary" comes from the practice of using canaries in coal mines to detect toxic gases—similarly, in software deployments, this method helps detect issues in the new module without impacting the entire user base.

It allows teams to test the new module under real-world conditions with minimal risk. If issues are detected, the deployment can be rolled back or adjusted before the changes are rolled out more widely.

## Benefits

- **Reduced Risk:** Changes are gradual, and you can roll back if something goes wrong.
- **Minimal Downtime:** Business operations continue without major interruptions.
- **Modernization:** Step-by-step upgrades ensure your system stays up-to-date.

The Strangler pattern is a safe and effective way to modernize your software systems, much like renovating a house room by room without having to move out!
