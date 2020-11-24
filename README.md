# mono-sandbox

Sandbox for playing around with monorepos configs and stuff...

### Why?

Nowadays we have to maintain several apps and those can have many versions generating a huge amount of code to maintain. Currently we are using
an approach that consists of one repo per app and divide the majors of this app in different branches. This approach is really natural and easy to understand because we are used to it on our day to day basis but what happens when we have to maintain many major versions? 

From experience I've discovered that this approach doesn't scale very well. For example, when we realeased the Render 8, I had to generate a new version of my apps to be compatible with it, so since I had 5 apps, with the new release it became 10 versions to maintain. 

Imagine that I have to execute a simple task like add support to a new language like Japanese, I have to generate one PR for each version, which are 10 different pull requests now and this goes on for tooling and other stuff. It's really easy to leave some version behind. 

**My theory** here is that keeping everything together we could do more with less PRs, do more cirurgical changes.

## Tools

- [`Lerna`](./lerna#readme)
