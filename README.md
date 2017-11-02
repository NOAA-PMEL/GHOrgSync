## GHOrgSync
Python script to clone and update (pull) repositories at a GitHub organization site to local 
repository directories.  Connects to GitHub as the current user.  Private repositories can 
be seen and cloned and updated if appropriate conditions are met.

#### Legal disclaimer:
*This repository is a software product and is not official communication 
of the National Oceanic and Atmospheric Administration, or the United 
States Department of Commerce.  All NOAA GitHub project code is provided 
on an 'as is' basis and the user assumes responsibility for its use.  Any 
claims against the Department of Commerce or Department of Commerce bureaus 
stemming from the use of this GitHub project will be governed by all 
applicable Federal law.  Any reference to specific commercial products, 
processes, or services by service mark, trademark, manufacturer, or 
otherwise, does not constitute or imply their endorsement, recommendation 
or favoring by the Department of Commerce.  The Department of Commerce 
seal and logo, or the seal and logo of a DOC bureau, shall not be used 
in any manner to imply endorsement of any commercial product or activity 
by DOC or the United States Government.*

### To see private repositories:
- If the environment variable `GITUSERTOKEN` is given and its value is not blank, authentication 
  is added to the requests for repository information using this value as the personal access 
  token.  If successful, information about both private and public repositories will be obtained.
  If the `GITUSERTOKEN` environment variable is not given or its value is blank, only information 
  about public repositories will be obtained.  
  See: https://help.github.com/articles/creating-a-personal-access-token-for-the-command-line/

- Uses SSH URLs (i.e., git@github.com/...) to clone the repositories.  In order to clone private 
  repositories, the current user's GitHub account must be configured with the user's SSH key.  
  See: https://help.github.com/articles/connecting-to-github-with-ssh/

### Usage:
    ghorgsync  orgname  localdir
#### where:
    orgname   is the GitHub organization name (e.g., NOAA-PMEL)  
    localdir  is the full-path of the directory containing a 'private'
              and a 'public' subdirectory which will contain the cloned   
              private and public, respectively, repository subdirectories
