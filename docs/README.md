# Mat Time website

Static marketing and support page for GitHub Pages. No packages, build step, external fonts, analytics or form service are required. All asset paths are relative so the site works under a repository URL such as `/bjj-tracker/`.

## Publish on GitHub Pages

1. Push the `docs` directory to the branch you want to publish.
2. In the GitHub repository, open **Settings → Pages**.
3. Under **Build and deployment**, choose **Deploy from a branch**.
4. Select that branch and the **/docs** folder, then save.
5. GitHub shows the published URL when deployment finishes.

Official guide: https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site

Use the published URL as the App Store marketing URL, and append `#support` for the support URL. If publishing to a separate repository, copy the contents of `docs` to its root and publish from `/ (root)` instead. Do not publish the entire app repository as the website.

## Preview locally

From the repository root:

```sh
python3 -m http.server 4173 --directory docs
```

Open http://localhost:4173/. Stop the server with Control-C when finished.

## When the app launches

Replace the “Coming soon to the App Store” span in `index.html` with a link to the real listing. Use Apple's official download badge if desired. Keep the existing support email unless it changes.

Once the final public site URL is known, use an absolute URL for `og:image` and add `og:url` and a canonical link in the document head. An absolute social image URL is needed for reliable sharing previews. The page itself already works without these additions.

The data section describes the current app and website behavior. It is not a standalone privacy policy. If you need a privacy policy URL for App Store Connect, prepare and review a separate policy before submission.

## Assets and content

Product images come from Mat Time's isolated demo captures and the existing Apple product bezel assets used by the screenshot editor. They contain example training data. WebP images are resized for the site; the larger App Store assets remain in `StoreScreenshots`.

Support: kemalenver+mattime@gmail.com. Help content follows the current in-app Help screen. Update it when app behavior changes.
