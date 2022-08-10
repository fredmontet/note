Google Takeout Tricks
=====================

When you take some fgiles out from Google Drive, you can download everything with Google
Takeout but all files are split and to recombine them manually is absolutely insane.
Thankfully, both zip files or tarballs can do the job for you.

In case of ZIP files
--------------------

    unzip '*.zip' -d complete-takeout

In case of Tarball
------------------

    cat takeout-20201023T123551Z-{001..011}.tgz | tar xzivf -

