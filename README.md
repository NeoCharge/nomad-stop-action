# Nomad Stop

Small GitHub Action that runs `nomad job stop ...` with the Nomad CLI.

## Usage

```yaml
name: Run Tests & Publish Image
on: [push]
jobs:
  deploy:
    name: Nomad Stop
    runs-on: ubuntu-latest
    steps:
      - name: Stop Nomad Job
        uses: neoCharge/nomad-stop-action
        with:
          token: '{{ secrets.YOUR_NOMAD_SECRET }}'
          address: '{{ secrets.YOUR_NOMAD_SERVER }}'
          job_name: 'name of your job to stop'
```

## Parameters

* `token`: passed as `-token=` to the `nomad job run` command ([see here how to get one](https://www.nomadproject.io/guides/security/acl.html#acl-tokens))
* `address`: public address of a nomad server (passed as `-address=`)
* `job_name`: name of the job to stop

## Todo

- [ ] Verify it works
- [ ] Probably something else
