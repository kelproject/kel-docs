# Deploying Kel Docs

Kel documentation is hosted on Google Cloud Storage. To deploy from the Lektor
cache, run:

    gsutil -m rsync -d -r $(lektor project-info --output-path) gs://docs.kelproject.com
    gsutil -m setmeta -h "Cache-Control:private,max-age=0,no-transform" gs://docs.kelproject.com/**

TODO: improve the `setmeta` command to cache some files.
