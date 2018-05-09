---
permalink: licensing
---

## Evaluation Period
- You can evaluate the library for several months before purchasing it.
- The latest version always contains a trial that expires at the **end of the month**. 
- You can extend your trial for several months by downloading the latest version at the begining of every month.
- If you want to use the library for personal use or educational purpose, it's possible by downloading the latest version once a month.

## How can I purchase the library?
- You can purchase the library [here](pricing)
- Upon purchase, you will receive an email with a license name and a license key.
- Make sure to check your **SPAM** folder if you don't receive the license within 24h.

## Setup License from config file
The license name and key can be added directly in the app.config or web.config file in the appSettings section.

{% include template-example.html %} 
{% highlight csharp %}
<appSettings>
	<add key="Z_LinqToSql_Plus_LicenseName" value="[licenseName]"/>
	<add key="Z_LinqToSql_Plus_LicenseKey" value="[licenseKey]"/>
</appSettings>
{% endhighlight %}

## Setup License from code
The license can be added directly in the code of your application. Make sure to follow recommendations about where to add this code.

{% include template-example.html %} 
{% highlight csharp %}
Z.LinqToSql.Plus.LinqToSqlManager.AddLicense([licenseName], [licenseKey]);
{% endhighlight %}

### Recommendations
- **Web App:** Use Application_Start in global.asax to activate your license.
- **WinForm App:** Use the main thread method to activate your license.
- **Win Service:** Use the OnStart method to activate your license

> Add the license before the first call to the library. Otherwise, the library will be enabled using the evaluation period.

## How can I check if my license is valid?
You can use the **ValidateLicense** method to check if the current license is valid or not.

{% include template-example.html %} 
{% highlight csharp %}
// CHECK if the license if valid for the default provider (SQL Server)
string licenseErrorMessage;
if (!Z.LinqToSql.Plus.LinqToSqlManager.ValidateLicense(out licenseErrorMessage))
{
    throw new Exception(licenseErrorMessage);
}
{% endhighlight %}
