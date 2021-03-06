# bosh.io stemcell resource

Tracks the versions of a stemcell on [bosh.io](https://bosh.io).

For example, to automatically consume `bosh-aws-xen-ubuntu-trusty-go_agent`:

```yaml
resources:
- name: aws-stemcell
  type: bosh-io-stemcell
  source:
    name: bosh-aws-xen-ubuntu-trusty-go_agent
```


## Source Configuration

* `name`: *Required.* The name of the stemcell.


## Behavior

### `check`: Check for new versions of the stemcell.

Detects new versions of the stemcell that have been published to bosh.io.


### `in`: Fetch a version of the stemcell.

Fetches a given stemcell, placing the following files in the destination:

* `version`: The version number of the stemcell.
* `url`: A URL that can be used to download the stemcell tarball.
* `stemcell.tgz`: The stemcell tarball, if the `tarball` param is `true`.

#### Parameters

* `tarball`: *Optional.* Default `true`. Fetch the stemcell tarball.
