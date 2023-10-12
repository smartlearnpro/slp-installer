# SmartLearnPro Web Installer

## Table of Contents
- [About](#about)
- [Requirements](#requirements)
- [Installation](#installation)
- [Configuration](#configuration)
- [Routes](#routes)
- [Usage](#usage)
- [Customization](#customization)
- [Folders](#folders)

## About

The SmartLearnPro Web Installer is a powerful Laravel package that simplifies the process of installing your application, much like popular content management systems such as WordPress. This installer is designed for users who may not have experience with Composer, SSH, or other technical tools. It offers an intuitive setup wizard with the following key features:

- **Server Requirement Checks**: It verifies whether your server meets the necessary requirements to run your application smoothly.

- **Folder Permission Checks**: It ensures that the required folders have the correct permissions for your application to function correctly.

- **Effortless Database Configuration**: You can set up your database configuration with ease, either by editing the `.env` file or through a user-friendly form wizard.

- **Database Migration**: It automatically migrates your database schema, so you don't have to worry about setting it up manually.

- **Database Seeding**: Seed your database tables quickly to populate them with sample data for testing.

## Requirements

Before you proceed, please ensure that your server environment meets the following requirements:

- [Laravel 8.0+](https://laravel.com/docs/installation): Your Laravel application should be version 8.0 or higher.

## Installation

Follow these steps to install the SmartLearnPro Web Installer:

1. Open your terminal and navigate to your project's root folder.

2. Run the following Composer command to add the package to your project:

    ```bash
    composer require smartlearnpro/smartlearnpro-installer
    ```

3. Register the package in the `config/app.php` file under the 'providers' array:

    ```php
    'providers' => [
        SmartLearnPro\SlpInstaller\Providers\SlpInstallerServiceProvider::class,
    ];
    ```

4. Publish the package's assets, views, configuration files, and language files by running the following command from your project's root folder:

    ```bash
    php artisan vendor:publish --provider="SmartLearnPro\SlpInstaller\Providers\SlpInstallerServiceProvider"
    ```

## Configuration

To customize the behavior of the installer, you can modify the configuration files located in the `/config/smartlearnproinstaller.php` directory.

## Routes

The installer provides a single route that you need to access to begin the installation process:

- `/install`

## Usage

### Installation Process

Follow these steps to install your application using the SmartLearnPro Web Installer:

1. Access the `/install` route in your web browser.

2. Follow the instructions provided in the setup wizard. It will guide you through checking server requirements, verifying folder permissions, and configuring your database.

3. Once the installation process is complete, an empty file named `installed` will be placed in the `/storage` directory.

4. If the `installed` file is present, the `/install` route will redirect to your application's homepage, indicating that the installation is successful.

## Customization

### Styling Your Installer

To style the installer to match your application's branding, use the following folder:

- `public/smartlearnprofiles`: This folder contains all the asset files responsible for styling your installer. You can override the default stylesheet `style.css` and add your own custom styles.

### Customizing the Installer View

The installer's appearance and content are fully customizable. You can make adjustments by editing the HTML code in this folder:

- `resources/views/smartlearnpro/installer`: This folder contains the HTML code for your installer. Customize it to align with your specific requirements.

Feel free to further customize your installer or expand this README with any additional information or sections you consider important.
