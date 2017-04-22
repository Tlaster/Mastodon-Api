# Mastodon.Net
.Net wrapper for [Mastodon](https://github.com/tootsuite/mastodon) Api  

# Sample  
```C#            
var domain = "mstdn.jp";
var clientName = "Mastodon.Net";
var userName = "";
var password = "";

var oauth = await Apps.Register(domain, clientName, scopes: new[] {Apps.SCOPE_READ, Apps.SCOPE_WRITE, Apps.SCOPE_FOLLOW});
var token = await OAuth.GetAccessTokenByPassword(domain, oauth.ClientId, oauth.ClientSecret, oauth.RedirectUri, userName, password, Apps.SCOPE_READ, Apps.SCOPE_WRITE, Apps.SCOPE_FOLLOW);

var timeline = await Timelines.Home(domain, token.AccessToken);
var notify = await Notifications.Fetching(domain, token.AccessToken);
var toot = await Statuses.Posting(domain, token.AccessToken, "Toot!");
```

# License
MIT