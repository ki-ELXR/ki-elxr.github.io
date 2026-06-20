# ki-ELXR's Website

Site Template from https://alshedivat.github.io/al-folio/

**TODO**
- Adjust the font and colors overriding scss files.

**Notes**
-   Website is deployed through github actions automatically after making a commit. It takes few minutes after the deploy action is completed for the site to fully update
-   Changes can be tested quickly in docker. Open up docker desktop, then in vscode, open the folder in a dev container. After the container is build and loaded, you can view the changes in near real time (1 minute or so) via http://localhost:8080/
-   Adjustsments are made to the files such that after the container is closed, the files are still updated

**Customization Notes**
- giscus comments: follow the instructions at https://giscus.app/
  - Add the following variables from giscus.app to _config.yml without quotes
  - data-repo -> repo
  - data-repo-id -> repo_id
  - data-category-id -> category_id
- socials icons and links in about page can be toggled at socials.yml

