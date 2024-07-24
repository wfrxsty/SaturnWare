local webh = "https://discord.com/api/webhooks/1265679987822821446/q8grhaf-1lY4QSVPGNbUwoTeuY5DI6hkEmsOr6aRxCTLNfT-v9sfmOkO7p17FlVfk1HQ"

local syn = {}
syn.request = request

local data = {
	['embeds'] = {
    	{
       		['title'] = 'Script executed!',
      		['description'] = '',
       		['fields'] = {
          		{name = 'User', value = "**"..game:GetService("Players").LocalPlayer.DisplayName.."**`(@"..game:GetService("Players").LocalPlayer.Name..")`"},
          		{name = "User ID", value = game:GetService("Players").LocalPlayer.UserId, inline = true},
                {name = "Account age", value = game:GetService("Players").LocalPlayer.AccountAge.. " days", inline = true},
          		{name = "JobsID", value = "```"..game.JobId.."```"},
                {name = 'Hwid', value = "```"..game:GetService("RbxAnalyticsService"):GetClientId().."```"},
			}
        }
    }
  }


local response = syn.request(
    {
        Url = webh,
        Method = 'POST',
        Headers = {
            ['Content-Type'] = 'application/json'
        },
        Body = game:GetService('HttpService'):JSONEncode(data)
    }
)
 
