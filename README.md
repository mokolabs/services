# SERVICES.YML
==============
A simple file format for documenting services used by web apps

Web apps often use a dozen or more third-party services and it can quickly become difficult to remember which services are used by the app, especially when working with larger numbers of apps.

## How it works

We can fix this by adding a list of services to our app.

The list should:
- Be named `SERVICES.YML`
- Be stored in the root of the app
- Use the YAML format when possible
- Use single words to describe service types
- Start with the hosting provider
- Place all other service types in alphabetical order
- Be updated when you change service providers

## Example

hosting: digitalocean
advertising: google
email:
  transactional: postmark
  spam: akismet
mapping:
  geocoding: google
  maps: apple
monitoring: sentry
storage:
  amazon:
    - cloudfront
    - s3

## FAQ

### Why not just use ENV variables?
ENV variables are used to store app secrets and other configs. We want a short list that we can read and understand in a glance.

### Why note just use a Gemfile?
Gemfiles are used to manage dependencies. Usually, most gems in a Gemfile are not service related, so that makes it harder to find the ones that are services.

### Do I have to use valid YAML?
No, not at all. Just start with YAML. But, if you find yourself needing to use non-YAML syntax, that's fine. This is *your* list.
