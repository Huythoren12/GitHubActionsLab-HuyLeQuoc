 GitHub Actions Lab - Huy Le Quoc

 Project Overview
This project demonstrates two GitHub Actions workflows for CI/CD automation. The first workflow shows job dependencies using the "needs" keyword where jobs execute sequentially. The second workflow demonstrates multi-platform testing where three independent jobs run in parallel on Ubuntu, Windows, and macOS without any dependencies between them.

 Workflow 1: Dependent Jobs Workflow
This workflow triggers on push to the main/master branch. It contains three jobs that run sequentially: build first, then test, then deploy. The test job depends on build using "needs: build", and deploy depends on test using "needs: test". This demonstrates how the "needs" keyword creates job dependencies, ensuring proper execution order. GitHub Actions UI shows arrows connecting the jobs in the dependency visualization.

Workflow 2: Multi-Platform Workflow
This workflow triggers on pull requests and runs three independent jobs simultaneously on Ubuntu, Windows, and macOS. Each job prints OS-specific information, creates a unique file, and displays its contents. The Windows job uses PowerShell commands while Linux and macOS use bash, demonstrating OS-specific behavior differences.

Challenges Faced and Solutions
The main challenge was a branch mismatch where code was pushed to master but workflows were configured for main, preventing workflows from triggering. This was resolved by updating workflow triggers to include both branches. Another challenge was Git sync issues between NetBeans and GitHub due to unrelated commit histories, solved by creating workflow files directly on GitHub's web interface instead of pushing from NetBeans.
