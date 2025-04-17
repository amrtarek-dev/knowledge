# Git submodule
Git submodules are a powerful feature that allows you to include a separate Git repository as a subdirectory within another Git repository.

This is particularly useful when you want to include a specific version of an external project within your own project.

## **Adding a Submodule**: 

To add a submodule to your Git repository, you use the **git submodule add** command followed by the URL of the repository and the path where you want it to reside within your project.

```bash
# git submodule add <URL_of_external_repository> <path_inside_your_project>
git submodule add https://github.com/example/repo.git external/repo
```
`

 ### **Initialising and Cloning**: 
 
 After adding the submodule, you need to initialise and clone its contents. Use the following commands:
 
```bash
git submodule update --init --recursive
```


## Working with Submodules:

### **Cloning a Repository with Submodules**: 

If you've cloned a repository that contains submodules, you need to initialize and update the submodules separately.

```bash
git clone <URL_of_your_project>
git submodule update --init --recursive
```


### **Updating Submodules**:

To update the submodule to the latest commit in its repository, navigate into the submodule directory and execute a **git pull**:

```bash
cd external/repo 
git pull origin main
```
  
### **Committing Submodule Changes**: 

When you make changes within the submodule, you need to commit those changes in the submodule's repository.

```bash 
cd external/repo 
# Make changes
git add . 
git commit -m "Updated submodule" 
git push origin main
```

### **Updating Submodule Reference in the Parent Repository**: 

If you've made changes in the submodule and want to update the parent repository to use the latest commit of the submodule:

```bash
cd /path/to/parent/repository
git submodule update --remote
```

 ### Important Points:

- Submodules are essentially references to a specific commit in another repository.
- When cloning a repository with submodules, the submodules directory might initially appear empty until you initialize and update them.
- When you commit changes in the parent repository that include submodule changes, it records the updated submodule commit reference.

Managing submodules can become complex, especially when collaborating with others or trying to keep multiple repositories in sync. It's crucial to have a good understanding of how submodules work and their implications on your project structure.