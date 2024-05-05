# Using TechDocs in Backstage

TechDocs is an essential tool in Backstage for managing technical documentation directly within the developer portal. It enables teams to maintain documentation alongside their codebase in a version-controlled system, ensuring documentation stays relevant and accessible.

## Overview

TechDocs facilitates a documentation-as-code approach, allowing documentation to be stored as Markdown files in your version control system. This setup helps keep your documentation synchronized with your project updates.

## Setting Up Documentation with TechDocs

### Step 1: Create Markdown Files

1. **Write Documentation**: Create Markdown (.md) files that contain your project documentation. You can use any text editor to write these files.
2. **Organize the Files**: Organize these Markdown files in a logical directory structure within your project repository. This might typically be in a `docs/` folder at the root of the repository.

### Step 2: Configure the MkDocs

Create a `mkdocs.yml` file in the root of your repository to define the structure of your documentation site. This configuration file specifies how the documentation should be built and displayed in Backstage.

Example `mkdocs.yml`:
```yaml
site_name: 'My Project Documentation'
nav:
  - Home: 'index.md'
  - Installation: 'install.md'
  - API Guide: 'api.md'
theme:
  name: 'material'
```
### Step 3: Add Documentation to Backstage

To make your documentation visible in Backstage, you need to integrate your repository with the TechDocs plugin:

1. **Prepare the Repository**: Ensure your repository with the Markdown files is accessible to Backstage. This usually means having your code and documentation hosted on a platform like GitHub, GitLab, or Bitbucket.
2. **Annotate the Backstage Catalog File**: Edit the `catalog-info.yaml` for your component to include a reference to your documentation. This annotation tells TechDocs where to find the documentation files.

```yaml
apiVersion: backstage.io/v1alpha1
kind: Component
metadata:
  name: my-service
  annotations:
    backstage.io/techdocs-ref: url:https://github.com/my-org/my-service
```
### Step 4: Build and View Documentation in Backstage

Once you've annotated your service, Backstage will automatically recognize and build the documentation site using TechDocs:

- **Access TechDocs in Backstage**: Navigate to the TechDocs section within Backstage.
- **Select Your Project**: Find and select your project to view its documentation.
- **View and Navigate Your Documentation**: Browse through the documentation pages as they are laid out in the `mkdocs.yml` file.

TechDocs compiles the Markdown files into a static site that is then served within Backstage, allowing you to access and navigate your project documentation directly:


