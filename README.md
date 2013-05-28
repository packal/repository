repository
==========

A general collection repository for Alfred2 Workflows and Themes

This repo serves two functions for the time being:

1 Development of the package manager
2 Holding space for contributed packages that the package manager interacts with

Currently, everything is mostly empty.

### Proposed Development Path

#### Priority

Let's develop the package manager first and then develop the website that we can be the submission, browsing, and discovery place that interacts with the github repo.

#### Accessing github

The github api puts too many limits on the requests (perhaps) in that an unauthenticated user has 60 queries / hour. An authenticated one has 5,000 / hour. The latter would probably do the trick across all users, but we obviously shouldn't be embedding authentication information in there. Hence, it seems best to follow the model from Alleyoop and require packages to have a sort of "manifest" in the base of their repo. There is a very rough draft of an xml schema in the repo. We could convert to JSON.

We should have a regular index of all of the packages in the base of the main repository. Upon the update of any package, the list can be regenerated. We can use that list for the package manager to grab to check for refreshes. Since getting this information is just a download, it doesn't count against using the api.

We could store the local copy as either a flat file, or we could store it in a SQL database.

Update information can be based either on the manifest (xml/JSON schema) or on a timestamp. The timestamp is probably better.

I'll write more on this later.

### Roadmap

Incomplete:

* Develop schema
* Develop package manager to update
* Develop package manager to download
* Develop package manager 
