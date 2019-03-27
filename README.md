# Arc Questions 2.0

### Is it possible for local Fusion instance to consume other local API's?
- **scenario:** Arc Fusion is running on `localhost` and a Node API is running on `localhost:4000`
- **why:** Building Arc PageBuilder widgets that consume API's we are developing (e.g. LocalGraf) in a local development environment
    - **implications for our demo on Friday:** We need to deploy an instance of our API somewhere to demo


### How is content cached?  In particular, how is data from a Content Source calling a 3rd party API cached?
- **scenario:** When using a Resolver (a Content Source that queries a GraphQL API + a Template), changes made to the API's records did not propogate to the Page articles
    - Changes we're eventually visible (2 hours later), but it's not clear what changed to make this happen: e.g. environment refresh, the caches' TTL policy, etc.
- **why:** If an Event is published incorrectly and must be deleted or changed, then we need a way to bust the cache to change the content without waiting
- **follow up:** How do we bust the cache?

### Where is the Arc PageBuilder content hosted in Sandbox, Production, or Development environments?
- **scenario:** When going through deployment process it's easy to deploy previews, but they're behind the Okta login.  I could not figure out how to deploy to a publicly-accessible URL.
- **context:** 
    - In local Fusion development environment, when a PageBuilder feature is developed, you can deploy it 1) to the PageBuilder Fusion preview (e.g. `localhost/pf/<feature>`) and 2) to the locally running Fusion instance (e.g. `localhost/<feature>`).
    - In Dev, Sandbox, and Production, after the feature page is *fully published*, it is only accessible through the `dmn.arcpublishing.com/pf/<feature>`
        - I expect them to be at `dmn.arcpublishing.com/<feature>` but they're not
    - **All URL's behind the `pf` URI segment require Okta login to see**
        - Only DMN developers can see them
- **follow up:** Can we go 100% through a feature deployment on Sandbox or Development?  Where are the publicly-accessible sites for each environment?