## Creating steps

Steps make up the wercker pipeline and can either be executed in the build or
deploy phase within the pipeline.

Examples of a build step are compilation of
your code, running your unit tests or performing jshint. A deploy step could be
the synchronization of static assets, for which we've created the s3sync step,
that takes some Amazon Web Services credentials and bucket information and
places these assets on Amazon S3.

### wercker-step.yml

Every step must contain a `wercker-step.yml` file, which is the manifest that
describes the properties for the step.

Here is an example of a `wercker-step.yml` that only holds the required fields:

```yaml
name: create-file
version: 0.9.6
description: create-file step
```

You can also add keywords to your step which increases discoverability:

```yaml
keywords:
  - file
  - text
  - create
```

### Step entry point

Every step is executed by executing a `run.sh` file, which should be present as well.
This file is responsible for the high-level
organization of the step's functionality. The actual step logic can be written
inside the `run.sh`. When you want to group things you can move your logic
to multiple shell scripts and call them from `run.sh`. You could also develop
a step in Ruby, Python or Node.js and use the `run.sh` to bootstrap this. A good example
of the latter is the [validate-wercker-step](https://github.com/wercker/step-validate-wercker-step).

### Step options

Steps can have options or parameters to receive input. For example, the `create-file` step
has the option `filename` that specifies the filename and where the file should be created.
Options are set as elements of the step attribute in `wercker.yml`. Here is an
example that uses the `create-file` step and specifies three options:

```yaml
- create-file:
    name: generate production robots.txt
    filename: ./_production/robots.txt
    content: |-
      User-agent: *
      Allow: /
```

The `name` option is default for every step and it allows the user to specify the
logical name for that step. In the example above `filename` and `content` are
`create-file` specific options. The value from options can be retrieved with the
`get_option` function:

    filename=`get_option filename`
    echo "Value for filename option: $filename"

- - -
> Want to learn more? Read more on this on the [docs](/docs/)

[&lsaquo; Notifications](/learn/steps/03_notifications.html "nav previous steps")
[Step registry &rsaquo;](/learn/steps/05_step-registry.html "nav next steps")