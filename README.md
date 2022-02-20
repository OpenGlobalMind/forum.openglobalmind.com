# forum.openglobalmind.com

A snapshot of the OGM Forum. Archived via wget on 2022-02-18.

Browseable version at <https://forum.openglobalmind.com/>.

Git version at <https://github.com/OpenGlobalMind/forum.openglobalmind.com>.

## Writeup

<https://forum.openglobalmind.com/> is now a static snapshot, and the EC2 server is stopped.

The snapshot is less than perfect, but much better than I was hoping for.  It was produced with `wget` and a careful selection of flags:

```shell
time wget --mirror --page-requisites --convert-links --restrict-file-names=windows --restrict-file-names=lowercase --adjust-extension --compression=auto --reject-regex "/search" --no-if-modified-since --no-check-certificate --execute robots=off --wait=1 --user-agent="Googlebot/2.1 (+http://www.google.com/bot.html)" https://forum.openglobalmind.com/
```

(via [How to Archive or Download a Discourse Forum with Wget \- Let's WP](https://letswp.io/download-discourse-forum-wget/), with modifications; `--restrict-file-names=windows --restrict-file-names=lowercase` is important, otherwise you can get `?` characters in the filename, which is not good for deployment)

The files are also in a GitHub repo, <https://github.com/OpenGlobalMind/forum.openglobalmind.com/> where you can download a zip archive of all the files.  That's also the way I hope to make the archive searchable (e.g., <https://github.com/OpenGlobalMind/forum.openglobalmind.com/search?q=foobar>), but GitHub is taking a long time to index the repo.  (There are a lot of HTML files, and also binary uploads and pre-resized versions of images, so the whole repo is kinda big.)

I also created <https://fjb-forum-openglobalmind-com.netlify.app/>, which archives the private FJB channels.  It is password-protected; I'll post the password in the "Free Jerry's Brain" private channel.  Its repo is <https://github.com/OpenGlobalMind/fjb-forum.openglobalmind.com/> (access restricted to FJB admins).

And lastly, I downloaded the Discourse-generated backup for the site, which consists of a SQL database dump and the uploaded files. Let me know if you'd like a copy.  It's ~84Mb.

There are a variety of ways to make the snapshot better, and I'll write down some of those, but I don't have plans to do more for now. Please also feel free to add issues at the repo: <https://github.com/OpenGlobalMind/forum.openglobalmind.com/issues>.
