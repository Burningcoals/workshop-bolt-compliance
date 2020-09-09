# Exercise #3 - Managing your inventory.yaml file

## Steps

- Edit inventory.yaml

- Replace the 000 in the `uri` field with your assigned server’s number for BOTH the Windows and Linux targets.

```
groups:
  - name: windows
    targets:
      - uri: bolt91620win000.classroom.puppet.com
        alias: www
    config:
      transport: winrm
      winrm:
        user: Administrator
        password: Puppetlabs!
        ssl: false
```

- Replace the SSH `key` field with the appropriate path to your 'boltshop' directory which contains an ssh key, boltkey.pem.

```
config:
      transport: ssh
      ssh:
        user: centos
        key: /path/to/boltshop/boltkey.pem
        host-key-check: false
        run-as: root
```

- Save and close inventory.yaml

- From your command shell (esure you are in the boltshop directory), run `bolt inventory show --targets all`

Sample Output:

```
PS C:\code\boltshop> bolt inventory show 
bolt0916win99.classroom.puppet.com
1 target
```

- To test connectivity to your nodes, run `bolt command run hostname --targets all`

- Verify you get a resonse from each target (1 Windows and 1 Linux) and there are no errors
