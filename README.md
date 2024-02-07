# SERVICES.YML

A simple file format for documenting services used by web apps

## The problem

Web apps often use a dozen or more third-party services and it can quickly become difficult to remember which services are used by the app, especially when working with many apps.

## The solution

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

```
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
```

## FAQ

### Why not just use ENV variables?
ENV variables are used to store app secrets and other configuration settings. We want a short list that we can read and understand in a glance.

### Why not just use a Gemfile?
Gemfiles are used to manage dependencies. Usually, most gems in a Gemfile are not service related, so that makes it harder to find the ones that are services.

### Why not just use a README?
README files are often very long and take a considerable amount of time to read.

### Do I have to use valid YAML?
No, not at all. Just start with YAML. But, if you need to use non-YAML syntax later, that's fine. This is *your* list.

### Is this format supposed to be machine-parseable?
Not really, but you're welcome to do so.
