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


## Action

### Use in ci

```yml
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      # build your plugin

      - name: Create/Update Jellyfin Release
        uses: LizardByte/jellyfin-plugin-repo@master
        with:
          github_token: ${{ secrets.GH_BOT_TOKEN }}
          committer_email: ${{ secrets.GH_BOT_EMAIL }}
          committer_name: ${{ secrets.GH_BOT_NAME }}
          release_tag: ${{ needs.setup_release.outputs.release_tag }}
          zipfile: <path_to_your_zipfile>
```

### Use action on release events

LizardByte uses the following workflow for Jellyfin plugins.
This allows us to remove versions when we delete a release, as we only keep a single pre-release.

See [update-jellyfin-release.yml](https://github.com/LizardByte/Themerr-jellyfin/.github/workflows/update-jellyfin-release.yml)
for an example.
