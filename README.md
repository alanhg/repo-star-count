## About

just use `${{steps.repo-stars.outputs.stars}}` to get repo's star-count.

### Example

```yml
...

on:
  # Triggers the workflow on push or pull request events but only for the master branch
  watch:
    action: started

steps:
- name: Star Count
  id: repo-stars
  uses: alanhe421/repo-star-count-action@master

...

```

If you want who star repo on star event. just use `${{github.event.sender.login}}`

For example , sender info
```json
{
  "sender": {
    "login": "Codertocat",
    "id": 21031067,
    "node_id": "MDQ6VXNlcjIxMDMxMDY3",
    "avatar_url": "https://avatars1.githubusercontent.com/u/21031067?v=4",
    "gravatar_id": "",
    "url": "https://api.github.com/users/Codertocat",
    "html_url": "https://github.com/Codertocat",
    "followers_url": "https://api.github.com/users/Codertocat/followers",
    "following_url": "https://api.github.com/users/Codertocat/following{/other_user}",
    "gists_url": "https://api.github.com/users/Codertocat/gists{/gist_id}",
    "starred_url": "https://api.github.com/users/Codertocat/starred{/owner}{/repo}",
    "subscriptions_url": "https://api.github.com/users/Codertocat/subscriptions",
    "organizations_url": "https://api.github.com/users/Codertocat/orgs",
    "repos_url": "https://api.github.com/users/Codertocat/repos",
    "events_url": "https://api.github.com/users/Codertocat/events{/privacy}",
    "received_events_url": "https://api.github.com/users/Codertocat/received_events",
    "type": "User",
    "site_admin": false
  }
}
```

Event doc see [here](https://docs.github.com/en/enterprise-server@3.2/developers/webhooks-and-events/webhooks/webhook-events-and-payloads#star)
