# manifesto
Here are some software engineering practices I would enstate. I do not expect you to agree to all of these and are more than encouraged to file an issue with any of them to facilitate further discussion. However, if I ever have the honor of employing your services as an engineer, I do expect them to be followed under standard baseball rules. On the flip side, if I ever have the honor of being considered for employment as an engineer by you, I would really appreciate our alignment on the following:

# The Goal
To abstract the "real-world" problem into a set of digital representations in order to build logic around it that is maintainable, robust, and scalable.

## Maintainability
- Easy to read, modify, and test

## Robust
- Appropriately executes the desired effect
- Allows for resilient error handling

## Scalable
- Presents a reasonable consideration of the future system load
- Need to hire operators of the software should not grow linearly with system load
- Prefer to scale horizontally and not vertically

## Timing
is everything. While all these principles matter with respect to engineering software, they must be considered with different weights based on the position and leverage of the company. (note: these numbers are made up and based on nothing more than intuition)
- Year 0-1: 0.80 Robust, 0.15 Maintainable, 0.05 Scalable: 
  - go for the MVP and build something where you won't have to jump on the console when presenting to investors
  - setting up a sexy setup developer infrastructure is how you can attract top talent when you get funded
  - it's fun and motivating to think about how the entire internet could consume your product, but don't spend more than 1 hr of your day's hack thinking about this
- Year 1-3: 0.50 Maintainable, 0.30 Scalable, 0.20 Robust: 
  - this is about as late as you can refactor anything before everything becomes anchored in; do it now
  - Get a good guage on what your data load will look as the business hits different stages and build accordingly
  - keep building out features as negotiated but it shouldn't fundamentally diverge from the MVP or else something's not right
- Year 3+: Congrats on getting a second round (or more) of funding! If you've done the first two phases correctly, you know much better about finding the right balance between these principles than my silly dogma.

# Tools
- No matter the problem, ensure that all possible options within the current toolset are exhaustively considered before proposing to introduce a new one (whether in-house or 3rd-party)
- If you really don't like a certain tool in favor of another, let the team know, but make sure you have fully prepared your case
  - If you are able to sell your pitch to more than 2/3 of the team, then we will develop a reasonable strategy to move forward with the change
  - However, if there is a consensus (of the same majority) that you have not done your due diligence, this will hurt your credibility as an engineer to the company

## Languages
- Infrastructure: 
  - Make for defining execution
  - Ansible for executing  
  - Markdown for docs
- Backend: 
  - Go is the microservice oriented language of choice for a reason, figure out why
- Frontend: 
  - React for web apps
  - React Native for mobile apps (unless the product is platform specific)

## Source Control
- All code should live in a Version Control System (VCS) except...
- Secure values (i.e. tokens, passwords, private keys) should NOT live in VCS
- Suggestions: BitBucket, GitHub, GitLab

### Forking
- Instead creating a branch from your shared repos, fork them and submit pull requests
  - This prevents your shared repos from having a polluted namespace of branches

## Build System
- Should be able to do the following:
  - Trigger work on certain events (i.e. vcs branch push, error alert)
  - Execute scripts to build, deploy, or support code
  - Appropriately alert the relevant party of any relevant events
- Suggestions: CircleCI, Jenkins, Teamcity, TravisCI

## Monitoring Dashboard
- Decide early what metrics matter to you
- Try to keep them all in one place as coherently as you can
- Suggestions: DataDog, Grafana, Splunk
