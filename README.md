# MFodaAppNuGet
Publishing packages
Article
02/03/2022
7 minutes to read
9 contributors


In this article
Publish to nuget.org
Managing package owners on nuget.org
Once you have created a package and have your .nupkg file in hand, it's a simple process to make it available to other developers, either publicly or privately:

Public packages are made available to all developers globally through nuget.org as described in this article (requires NuGet 4.1.0+).
Private packages are available to only a team or organization, by hosting them either a file share, a private NuGet server, Azure Artifacts, or a third-party repository such as myget, ProGet, Nexus Repository, and Artifactory. For additional details, see Hosting Packages Overview.
This article covers publishing to nuget.org; for publishing to Azure Artifacts, see Package Management.

Publish to nuget.org
For nuget.org, you must sign in with a Microsoft account, with which you'll be asked to register the account with nuget.org.

NuGet sign in location

Next, you can either upload the package through the nuget.org web portal, push to nuget.org from the command line (requires nuget.exe 4.1.0+) , or publish as part of a CI/CD process through Azure DevOps Services, as described in the following sections.

Web portal: use the Upload Package tab on nuget.org
Select Upload on the top menu of nuget.org and browse to the package location.

Upload a package on nuget.org

nuget.org tells you if the package name is available. If it isn't, change the package identifier in your project, rebuild, and try the upload again.

If the package name is available, nuget.org opens a Verify section in which you can review the metadata from the package manifest. If you included a readme file in your package, check out the preview to ensure all content is being rendered properly. To change any of the metadata, edit your project (project file or .nuspec file), rebuild, recreate the package, and upload again.

When all the information is ready, select the Submit button

Command line
To push packages to nuget.org, you first need an API key, which is created on nuget.org. You must use either dotnet.exe (.NET Core), or nuget.exe v4.1.0 or above, which implement the required NuGet protocols. For more information, see .NET Core, nuget.exe, and NuGet protocols.

Create API keys
Sign into your nuget.org account or create an account if you don't have one already.

For more information on creating your account, see Individual accounts.

Select your user name (on the upper right), then select API Keys.

Select Create, provide a name for your key, select Select Scopes > Push. Enter * for Glob pattern, then select Create. (See below for more about scopes.)

Once the key is created, select Copy to retrieve the access key you need in the CLI:

Copying the API key to the clipboard

