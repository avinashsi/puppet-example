# Modules

### Folder Structure 

/etc/puppet/modules/[module_name]

Puppet Enterprise
/etc/puppetlabs/puppet/modules/[module_name]

```
├── files
├── manifests
│   ├── groups
│   │   ├── finance.pp (example)
│   │   └── wheel.pp (example)
│   └── init.pp
├── templates
└── tests
    └── init.pp
```

- files - Stores files needed by nodes
- manifests - Should always have a init.pp
- templates - 
- tests - 

#### init.pp
```
class localusers {
	user 
...
}
```

#### groups/wheel.pp

```
class localusers::groups::wheel {
...
}
```
*** Note:***  *The "::" is autoload. Refers to subfolders in the main module*

#### test/init.pp

```
include localusers
include localusers::groups::wheel
```