# jellyfin-plugin-repo

This repository hosts LizardByte's Jellyfin plugins in gh-pages. Additionally, there is a re-usable GitHub action
that can be used to publish your own plugins to your own gh-pages repository. See [action.yml](action.yml) for details.

## Install LizardByte Jellyfin repository

1. Open the Jellyfin dashboard
2. Navigate to the `Plugins` menu
3. Click the `Repositories` tab
4. Click the `+` button
5. Enter one of the following URLs:

    *Primary*
    ```txt
    https://app.lizardbyte.dev/jellyfin-plugin-repo/manifest.json
    ```

    *Alternate*
    ```txt
    https://lizardbyte.github.io/jellyfin-plugin-repo/manifest.json
    ```

    *It should look like this:*
    ![Add Repository](/docs/images/jellyfin_new_repository.png)

6. Click `Save`
7. Confirm the warning

    ![Confirm Warning](/docs/images/jellyfin_confirm_third_party_plugin.png)

8. Select the `Catalog` tab to see the newly added plugins.
