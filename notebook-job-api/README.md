# Example Job API

This notebook is an example of one you might want to run as an API. We will deploy it as a Saturn Cloud Job which has an HTTP endpoint to trigger it running.

The only thing the job does in this example is writes a line to the logs (you probably want to make it do more interesting things in practice).

In Saturn Cloud, create a new **Job resource** that has the following command:

```bash
jupyter nbconvert --to python --output example.py materials/notebook-job-api/example.ipynb && python materials/notebook-job-api/example.py
```

Then, in the **git repositories** of the resource, use this materials resource as a connected repository (`git@github.com:saturncloud/materials.git`).

This will set up a job that when triggered runs the notebook
