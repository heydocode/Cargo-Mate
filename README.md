# Cargo-Mate

**Cargo-Mate** is a Cargo plugin designed to streamline your Rust projects by managing workflows for multiple target destinations. With Cargo-Mate, you can easily maintain a universal library for all targets and ensure your build process is optimized, efficient, and tailored to your specific needs.

## Why Cargo-Mate?

In a multi-target Rust project, maintaining separate configurations and code for each platform can become cumbersome. **Cargo-Mate** simplifies this process by allowing you to:
- Manage workflows that are contextually appropriate for each target (e.g., excluding desktop-specific features in mobile builds).
- Automatically sync changes from a universal library across all target folders.
- Log errors, warnings, and TODOs effectively for better project management.
- Run a binary that links all parts of the project for easy execution.

## Design Goals

- **Universal Library Integration**: A universal library for all targets will be imported into each target. This ensures that changes made in the universal codebase are reflected across all target folders, reducing code duplication and improving maintainability.

- **Cross-Target Builds**: Provide a single command to build the project for all supported targets, streamlining the development process.

- **Code Optimization**: Implement automated refactoring steps that run during each cross-target build, ensuring that the code adheres to best practices and is free of unnecessary complexity.

- **Error and Warning Logging**: After building for all targets, the plugin will gather and log all errors, warnings, and TODOs, allowing developers to address issues systematically.

- **Dynamic Dependency Management**: Parse and modify `Cargo.toml` to adjust dependencies based on target platforms automatically, ensuring compatibility and reducing conflicts.

- **Change Detection and Syncing**: Monitor the universal folder for changes and automatically propagate those changes to the target folders while avoiding duplication of similar code.

- **Binary Linking**: Generate a binary that links all parts of the project, allowing you to execute the entire workflow with a simple `cargo run`.

- **Organized Project Structure**: Create dedicated folders for error logs, caching, and project settings at the root level of the project for better management and organization.

## To-Do List for Implementation

- [ ] Create the basic structure of the Cargo plugin with necessary files and folders.
- [ ] Implement the functionality to clone a GitHub repository.
- [ ] Develop the mechanism to replace occurrences of the project template name in files.
- [ ] Write the command to build for multiple targets and capture build output.
- [ ] Integrate automated refactoring tools (e.g., rustfmt) into the build process.
- [ ] Implement a logging system for errors, warnings, and TODO comments found in the project.
- [ ] Develop a syncing mechanism to apply changes from the universal folder to target folders.
- [ ] Set up dynamic dependency management in `Cargo.toml` based on target platforms.
- [ ] Create a binary that links all parts of the project and runs the necessary commands on `cargo run`.
- [ ] Create dedicated folders for error logs, caching, and project settings.
- [ ] Update the plugin to log errors and warnings in the new `error_logs` folder.
- [ ] Implement caching mechanisms in the `cache` folder to store intermediary files and states.
- [ ] Develop a configuration management system using the `settings` folder for user preferences and settings.
- [ ] Write comprehensive tests to ensure all functionalities work correctly across different scenarios.
- [ ] Create detailed documentation for users to guide them through installation and usage.

## Installation

To install Cargo-Mate, add it as a plugin in your Cargo configuration:

```toml
[plugins]
cargo-mate = { path = "path/to/cargo-mate" }
```

## Usage

Once installed, you can use Cargo-Mate to build your project across multiple targets with a single command:

```bash
cargo mate build
```

You can also run the project using the generated binary (you have to execute cargo mate at least once):

```bash
cargo run
```

## Contribution

Contributions are welcome! If you have ideas for features or improvements, please open an issue or submit a pull request.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
### Additional Notes
- Feel free to customize any section further to match your style or specific implementation details.
- Ensure to add any relevant sections like "Examples" or "FAQs" if you feel they would benefit users.
- As you implement features, update the "To-Do List" to reflect completed tasks and adjust any installation or usage instructions accordingly.
- Don't hesitate to create an issue if you think you have to be mentioned here because of your pull requests, ideas, etc!
