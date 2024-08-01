
## Install Git-LFS
`
```
git lfs install
```

## Declare File Types to track

```
git lfs track ".*ext"
```


## Untracking Files

To stop tracking a file type, you can use the `git lfs untrack` command:

```
git lfs untrack "*.psd"
```
Now make sure `.gitattributes` is tracked:
```
git add .gitattributes
```



## Fetching and Cloning

When cloning a repository that uses Git LFS, the large files will be fetched automatically. If you already have the repository and want to pull the latest large files, use:

```
git lfs fetch
```


## Track the File with Git LFS

```
git lfs track "large_image.png"

```


## List Tracked Files with Git LFS

```
git lfs ls-files
```

