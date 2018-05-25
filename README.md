# npm Demo

## Part 1: Installation and Upgrading of Packages

1. Install a package locked at version
```
npm i react@15.6.0 -E --save
```

2. Demo upgrade does nothing
```
npm upgrade
```

3. Install same package unlocked (notice package-lock.json didn't change)
```
npm i react@15.6.0 --save
```

4. Demo upgrade does something
```
npm upgrade
# => React now at 15.6.2
```

5. Install react 15.5.0 to demo ~ and ^ locking
```
npm i react@15.5.0 -E --save
```

6. Demo ~ bound package upgrade
```
# Change "15.5.0" to "~15.5.0"
> npm upgrade
# => React 15.5.4 installed, i.e. patch version locked
```

7. Demo ^ bound package upgrade
```
# Changed "~15.5.4" to "^15.5.4"
> npm upgrade
# => React 15.6.2 installed, i.e. minor + patch version locked
```

**Note:** There is no way to unbound a package so `npm upgrade` does a major version patch. Know
how your npm package works. For instance, if minor version bumps can introduce breaking changes,
lock your package with a `~`. If only major version bumps can introduce breaking changes, lock your
package with a `^`. If the package is highly unstable, you probably shouldn't install it but
definitely hard version lock it with the `-E` option.

8. Major version upgrade is done via the install command (bad contrived example)
```
> npm i react@16.4.0 --save
```
