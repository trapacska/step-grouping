----------------------------------------------
bitrise-io/steps-xcode-archive:
----------------------------------------------

▼ export_method: auto-detect [auto-detect app-store ad-hoc enterprise development]
  team_id: 
▼ upload_bitcode: yes [yes no]
▼ compile_bitcode: yes [yes no]

[Export Options (debug)]
  custom_export_options_plist_content: 

[Config]
* project_path: $BITRISE_PROJECT_PATH
* scheme: $BITRISE_SCHEME
  configuration: 

[Force Signing Build Settings]
  force_team_id: 
  force_code_sign_identity: 
  force_provisioning_profile_specifier: 
  force_provisioning_profile: 

[Debug]
* output_dir: $BITRISE_DEPLOY_DIR
  workdir: $BITRISE_SOURCE_DIR
▼ is_clean_build: no [yes no]
▼ output_tool: xcpretty [xcpretty xcodebuild]
  xcodebuild_options: 
▼ is_export_xcarchive_zip: no [yes no]
▼ export_all_dsyms: yes [yes no]
  artifact_name: ${scheme}
▼ verbose_log: yes [yes no]

[Deprecated]
▼ use_deprecated_export: no [yes no]


##############################################

* project_path: $BITRISE_PROJECT_PATH
* scheme: $BITRISE_SCHEME
  configuration: 
▼ export_method: auto-detect [auto-detect app-store ad-hoc enterprise development]
  team_id: 
▼ compile_bitcode: yes [yes no]
▼ upload_bitcode: yes [yes no]

[Force Build Settings]
  force_team_id: 
  force_code_sign_identity: 
  force_provisioning_profile_specifier: 
  force_provisioning_profile: 
  
[Debug]
  custom_export_options_plist_content: 
  artifact_name: ${scheme}
  xcodebuild_options: 
  workdir: $BITRISE_SOURCE_DIR
  * output_dir: $BITRISE_DEPLOY_DIR
▼ is_clean_build: no [yes no]
▼ output_tool: xcpretty [xcpretty xcodebuild]
▼ is_export_xcarchive_zip: no [yes no]
▼ export_all_dsyms: yes [yes no]
▼ verbose_log: yes [yes no]
▼ use_deprecated_export: no [yes no]

----------------------------------------------
----------------------------------------------

----------------------------------------------
bitrise-io/steps-activate-ssh-key:
----------------------------------------------

  ssh_rsa_private_key: $SSH_RSA_PRIVATE_KEY
  ssh_key_save_path: $HOME/.ssh/bitrise_step_activate_ssh_key
▼ is_remove_other_identities: true [true false]


##############################################

  ssh_rsa_private_key: $SSH_RSA_PRIVATE_KEY
  ssh_key_save_path: $HOME/.ssh/bitrise_step_activate_ssh_key
▼ is_remove_other_identities: true [true false]

no change
----------------------------------------------
----------------------------------------------

----------------------------------------------
bitrise-io/steps-git-clone:
----------------------------------------------

* repository_url: $GIT_REPOSITORY_URL
* clone_into_dir: $BITRISE_SOURCE_DIR

[Clone Config]
  commit: $BITRISE_GIT_COMMIT
  tag: $BITRISE_GIT_TAG
  branch: $BITRISE_GIT_BRANCH
  branch_dest: $BITRISEIO_GIT_BRANCH_DEST
  pull_request_id: $PULL_REQUEST_ID
  pull_request_repository_url: $BITRISEIO_PULL_REQUEST_REPOSITORY_URL
  pull_request_merge_branch: $BITRISEIO_PULL_REQUEST_MERGE_BRANCH
▼ manual_merge: yes [yes no]

[Debug]
▼ reset_repository: No [No Yes]
  clone_depth: 
  build_url: $BITRISE_BUILD_URL
  build_api_token: $BITRISE_BUILD_API_TOKEN
▼ update_submodules: yes [yes no]


##############################################

* repository_url: $GIT_REPOSITORY_URL
* clone_into_dir: $BITRISE_SOURCE_DIR

[Clone Config]
  commit: $BITRISE_GIT_COMMIT
  tag: $BITRISE_GIT_TAG
  branch: $BITRISE_GIT_BRANCH
  branch_dest: $BITRISEIO_GIT_BRANCH_DEST
  pull_request_id: $PULL_REQUEST_ID
  pull_request_repository_url: $BITRISEIO_PULL_REQUEST_REPOSITORY_URL
  pull_request_merge_branch: $BITRISEIO_PULL_REQUEST_MERGE_BRANCH
▼ update_submodules: yes [yes no]
  clone_depth: 

[Debug]
▼ reset_repository: No [No Yes]
▼ manual_merge: yes [yes no]
  build_url: $BITRISE_BUILD_URL
  build_api_token: $BITRISE_BUILD_API_TOKEN


----------------------------------------------
----------------------------------------------

----------------------------------------------
bitrise-io/steps-certificate-and-profile-installer:
----------------------------------------------



[Config]
  certificate_url: $BITRISE_CERTIFICATE_URL
  certificate_passphrase: $BITRISE_CERTIFICATE_PASSPHRASE
  provisioning_profile_url: $BITRISE_PROVISION_URL
* keychain_path: $HOME/Library/Keychains/login.keychain
* keychain_password: $BITRISE_KEYCHAIN_PASSWORD

[Debug]
  default_certificate_url: $BITRISE_DEFAULT_CERTIFICATE_URL
  default_certificate_passphrase: $BITRISE_DEFAULT_CERTIFICATE_PASSPHRASE
  default_provisioning_profile_url: $BITRISE_DEFAULT_PROVISION_URL


##############################################

  certificate_url: $BITRISE_CERTIFICATE_URL
  certificate_passphrase: $BITRISE_CERTIFICATE_PASSPHRASE
  provisioning_profile_url: $BITRISE_PROVISION_URL
* keychain_path: $HOME/Library/Keychains/login.keychain
* keychain_password: $BITRISE_KEYCHAIN_PASSWORD

[Default Codesign Files]
▼ install_defaults: true [true false]
  default_certificate_url: $BITRISE_DEFAULT_CERTIFICATE_URL
  default_certificate_passphrase: $BITRISE_DEFAULT_CERTIFICATE_PASSPHRASE
  default_provisioning_profile_url: $BITRISE_DEFAULT_PROVISION_URL

----------------------------------------------
----------------------------------------------

----------------------------------------------
bitrise-io/steps-deploy-to-bitrise-io:
----------------------------------------------



[Config]
* deploy_path: $BITRISE_DEPLOY_DIR
▼ is_compress: false [true false]
  zip_name: 
▼ is_enable_public_page: true [true false]

[Notification]
  notify_user_groups: everyone
  notify_email_list: 

[Debug]
* build_url: $BITRISE_BUILD_URL
* build_api_token: $BITRISE_BUILD_API_TOKEN


##############################################

* deploy_path: $BITRISE_DEPLOY_DIR
  notify_user_groups: everyone
  notify_email_list: 
▼ is_enable_public_page: true [true false]
▼ is_compress: false [true false]

[Debug]
  zip_name: 
* build_url: $BITRISE_BUILD_URL
* build_api_token: $BITRISE_BUILD_API_TOKEN


----------------------------------------------
----------------------------------------------

----------------------------------------------
bitrise-io/steps-script:
----------------------------------------------

* content: #!/usr/bin/env bash
# fail if any commands fails
set -e
# debug log
set -x

# write your script here
echo "Hello World!"

# or run a script from your repository, like:
# bash ./path/to/script.sh
# not just bash, e.g.:
# ruby ./path/to/script.rb

[Config]
* runner_bin: /bin/bash
  working_dir: $BITRISE_SOURCE_DIR
  script_file_path: 

[Debug]
▼ is_debug: no [no yes]


##############################################

* content: #!/usr/bin/env bash
# fail if any commands fails
set -e
# debug log
set -x

# write your script here
echo "Hello World!"

# or run a script from your repository, like:
# bash ./path/to/script.sh
# not just bash, e.g.:
# ruby ./path/to/script.rb
* runner_bin: /bin/bash

[Debug]
  working_dir: $BITRISE_SOURCE_DIR
  script_file_path: 
▼ is_debug: no [no yes]


----------------------------------------------
----------------------------------------------

----------------------------------------------
bitrise-io/steps-gradle-runner:
----------------------------------------------



[Export Config]
  apk_file_include_filter: *.apk
  apk_file_exclude_filter: *unaligned.apk
*Test*.apk

  test_apk_file_include_filter: *Test*.apk
  test_apk_file_exclude_filter: 
  mapping_file_include_filter: */mapping.txt
  mapping_file_exclude_filter: 

[Debug]
▼ cache_level: only_deps [all only_deps none]
  gradle_options: --stacktrace --no-daemon

[Config]
  gradle_file: $GRADLE_BUILD_FILE_PATH
* gradle_task: assemble
* gradlew_path: $GRADLEW_PATH


##############################################

* gradlew_path: $GRADLEW_PATH
  gradle_file: $GRADLE_BUILD_FILE_PATH
* gradle_task: assemble
  gradle_options: --stacktrace --no-daemon
▼ cache_level: only_deps [all only_deps none]

[Output Filters]
  apk_file_include_filter: *.apk
  apk_file_exclude_filter: *unaligned.apk\n*Test*.apk\n
  test_apk_file_include_filter: *Test*.apk
  test_apk_file_exclude_filter: 
  mapping_file_include_filter: */mapping.txt
  mapping_file_exclude_filter: 

----------------------------------------------
----------------------------------------------

----------------------------------------------
bitrise-io/steps-fastlane:
----------------------------------------------

* lane: 
  work_dir: $BITRISE_SOURCE_DIR
▼ update_fastlane: true [true false]


##############################################

* lane: 
  work_dir: $BITRISE_SOURCE_DIR
▼ update_fastlane: true [true false]

no change
----------------------------------------------
----------------------------------------------

----------------------------------------------
bitrise-io/steps-cocoapods-install:
----------------------------------------------

* source_root_path: $BITRISE_SOURCE_DIR
  podfile_path: 
▼ is_update_cocoapods: false [true false]
  install_cocoapods_version: 
▼ verbose: true [true false]
▼ is_cache_disabled: false [true false]


##############################################

* source_root_path: $BITRISE_SOURCE_DIR
  podfile_path: 
▼ is_update_cocoapods: false [true false]
  install_cocoapods_version: 
▼ verbose: true [true false]
▼ is_cache_disabled: false [true false]

no change
----------------------------------------------
----------------------------------------------

----------------------------------------------
bitrise-io/steps-xcode-test:
----------------------------------------------



[Testing]
* simulator_device: iPhone 6s Plus
* simulator_os_version: latest
▼ simulator_platform: iOS Simulator [iOS Simulator tvOS Simulator]
▼ export_uitest_artifacts: false [true false]
▼ generate_code_coverage_files: no [yes no]

[Config]
* project_path: $BITRISE_PROJECT_PATH
* scheme: $BITRISE_SCHEME

[Debug]
  workdir: $BITRISE_SOURCE_DIR
▼ is_clean_build: no [yes no]
▼ output_tool: xcpretty [xcpretty xcodebuild]
  xcodebuild_test_options: 
▼ single_build: true [true false]
▼ should_build_before_test: yes [yes no]
▼ should_retry_test_on_fail: no [yes no]
  xcpretty_test_options: --color --report html --output "${BITRISE_DEPLOY_DIR}/xcode-test-results-${BITRISE_SCHEME}.html"
▼ wait_for_simulator_boot: yes [yes no]


##############################################

* project_path: $BITRISE_PROJECT_PATH
* scheme: $BITRISE_SCHEME
* simulator_device: iPhone 6s Plus
* simulator_os_version: latest
▼ simulator_platform: iOS Simulator [iOS Simulator tvOS Simulator]
▼ export_uitest_artifacts: false [true false]
▼ generate_code_coverage_files: no [yes no]

[Debug]
▼ wait_for_simulator_boot: yes [yes no]
  workdir: $BITRISE_SOURCE_DIR
▼ is_clean_build: no [yes no]
▼ output_tool: xcpretty [xcpretty xcodebuild]
  xcodebuild_test_options: 
▼ single_build: true [true false]
▼ should_build_before_test: yes [yes no]
▼ should_retry_test_on_fail: no [yes no]
  xcpretty_test_options: --color --report html --output "${BITRISE_DEPLOY_DIR}/xcode-test-results-${BITRISE_SCHEME}.html"


----------------------------------------------
----------------------------------------------

----------------------------------------------
bitrise-community/steps-ionic-archive:
----------------------------------------------

▼ platform: ios,android [ios,android ios android]
▼ configuration: release [release debug]
▼ target: device [device emulator]
  build_config: $BITRISE_CORDOVA_BUILD_CONFIGURATION
  options: 
  ionic_username: 
  ionic_password: 
  ionic_version: 
  cordova_version: 
  cordova_ios_version: 
  cordova_android_version: 
* workdir: $BITRISE_SOURCE_DIR


##############################################

▼ platform: ios,android [ios,android ios android]
▼ configuration: release [release debug]
▼ target: device [device emulator]
* workdir: $BITRISE_SOURCE_DIR
  build_config: $BITRISE_CORDOVA_BUILD_CONFIGURATION
  options: 
  ionic_username: 
  ionic_password: 
  
[DEBUG]
  ionic_version: 
  cordova_version: 
  cordova_ios_version: 
  cordova_android_version: 


----------------------------------------------
----------------------------------------------

----------------------------------------------
bitrise-community/steps-generate-cordova-build-configuration:
----------------------------------------------

▼ configuration: debug [release debug]
  development_team: 
  code_sign_identity: 
  provisioning_profile: 
▼ package_type: none [none development enterprise ad-hoc app-store]
  keystore_url: $BITRISEIO_ANDROID_KEYSTORE_URL
  keystore_password: $BITRISEIO_ANDROID_KEYSTORE_PASSWORD
  keystore_alias: $BITRISEIO_ANDROID_KEYSTORE_ALIAS
  private_key_password: $BITRISEIO_ANDROID_KEYSTORE_PRIVATE_KEY_PASSWORD


##############################################

▼ configuration: debug [release debug]
  development_team: 
  code_sign_identity: 
  provisioning_profile: 
▼ package_type: none [none development enterprise ad-hoc app-store]
  keystore_url: $BITRISEIO_ANDROID_KEYSTORE_URL
  keystore_password: $BITRISEIO_ANDROID_KEYSTORE_PASSWORD
  keystore_alias: $BITRISEIO_ANDROID_KEYSTORE_ALIAS
  private_key_password: $BITRISEIO_ANDROID_KEYSTORE_PRIVATE_KEY_PASSWORD

no change
----------------------------------------------
----------------------------------------------

----------------------------------------------
bitrise-community/steps-jasmine-runner:
----------------------------------------------

  workdir: $BITRISE_SOURCE_DIR
  options: 


##############################################

  workdir: $BITRISE_SOURCE_DIR
  options: 

no change
----------------------------------------------
----------------------------------------------

----------------------------------------------
bitrise-steplib/steps-cache-pull:
----------------------------------------------

  workdir: $BITRISE_SOURCE_DIR
▼ is_debug_mode: false [true false]
* cache_api_url: $BITRISE_CACHE_API_URL


##############################################

  workdir: $BITRISE_SOURCE_DIR
▼ is_debug_mode: false [true false]
* cache_api_url: $BITRISE_CACHE_API_URL

no change
----------------------------------------------
----------------------------------------------

----------------------------------------------
bitrise-steplib/steps-cache-push:
----------------------------------------------

  cache_paths: $BITRISE_CACHE_DIR

  ignore_check_on_paths: 
  workdir: $BITRISE_SOURCE_DIR
▼ fingerprint_method: file-content-hash [file-content-hash file-mod-time]
▼ is_debug_mode: false [true false]
▼ compress_archive: false [true false]
* bitrise_cache_include_paths: $BITRISE_CACHE_INCLUDE_PATHS
* bitrise_cache_exclude_paths: $BITRISE_CACHE_EXCLUDE_PATHS
* cache_api_url: $BITRISE_CACHE_API_URL
* compare_cache_info_path: $BITRISE_CACHE_INFO_PATH


##############################################

  cache_paths: $BITRISE_CACHE_DIR
  ignore_check_on_paths: 
  workdir: $BITRISE_SOURCE_DIR

[Config]
▼ fingerprint_method: file-content-hash [file-content-hash file-mod-time]
▼ compress_archive: false [true false]
* bitrise_cache_include_paths: $BITRISE_CACHE_INCLUDE_PATHS
* bitrise_cache_exclude_paths: $BITRISE_CACHE_EXCLUDE_PATHS
* cache_api_url: $BITRISE_CACHE_API_URL
* compare_cache_info_path: $BITRISE_CACHE_INFO_PATH
▼ is_debug_mode: false [true false]


----------------------------------------------
----------------------------------------------

----------------------------------------------
bitrise-steplib/steps-install-missing-android-tools:
----------------------------------------------



[Config]
* gradlew_path: $GRADLEW_PATH


##############################################


* gradlew_path: $GRADLEW_PATH


----------------------------------------------
----------------------------------------------

----------------------------------------------
bitrise-steplib/steps-carthage:
----------------------------------------------

  github_access_token: $GITHUB_ACCESS_TOKEN
  carthage_command: bootstrap
  carthage_options: 


##############################################

  carthage_command: bootstrap
  carthage_options: 
  github_access_token: $GITHUB_ACCESS_TOKEN

----------------------------------------------
----------------------------------------------

----------------------------------------------
bitrise-steplib/steps-recreate-user-schemes:
----------------------------------------------

* project_path: 


##############################################

* project_path: 

no change
----------------------------------------------
----------------------------------------------

----------------------------------------------
bitrise-steplib/steps-xamarin-user-management:
----------------------------------------------

* build_slug: $BITRISE_BUILD_SLUG


##############################################

* build_slug: $BITRISE_BUILD_SLUG

no change
----------------------------------------------
----------------------------------------------

----------------------------------------------
bitrise-steplib/steps-nuget-restore:
----------------------------------------------

* xamarin_solution: $BITRISE_PROJECT_PATH
  nuget_version: latest


##############################################

* xamarin_solution: $BITRISE_PROJECT_PATH
  nuget_version: latest

no change
----------------------------------------------
----------------------------------------------

----------------------------------------------
bitrise-steplib/steps-xamarin-components-restore:
----------------------------------------------

* xamarin_solution: $BITRISE_PROJECT_PATH


##############################################

* xamarin_solution: $BITRISE_PROJECT_PATH

no change
----------------------------------------------
----------------------------------------------

----------------------------------------------
bitrise-steplib/steps-xamarin-archive:
----------------------------------------------



[Config]
* xamarin_solution: $BITRISE_PROJECT_PATH
* xamarin_configuration: $BITRISE_XAMARIN_CONFIGURATION
* xamarin_platform: $BITRISE_XAMARIN_PLATFORM
  project_type_whitelist: android,ios,macos,tvos

[Debug]
▼ build_tool: msbuild [msbuild xbuild]
  ios_build_command_custom_options: 
  android_build_command_custom_options: 
  tvos_build_command_custom_options: 
  macos_build_command_custom_options: 


##############################################

* xamarin_solution: $BITRISE_PROJECT_PATH
* xamarin_configuration: $BITRISE_XAMARIN_CONFIGURATION
* xamarin_platform: $BITRISE_XAMARIN_PLATFORM
  project_type_whitelist: android,ios,macos,tvos

[Debug]
▼ build_tool: msbuild [msbuild xbuild]
  ios_build_command_custom_options: 
  android_build_command_custom_options: 
  tvos_build_command_custom_options: 
  macos_build_command_custom_options: 


----------------------------------------------
----------------------------------------------

----------------------------------------------
bitrise-steplib/steps-xcode-archive-mac:
----------------------------------------------



[force archive codesign settings]
  force_team_id: 
  force_code_sign_identity: 
  force_provisioning_profile_specifier: 
  force_provisioning_profile: 

[step output configs]
▼ output_tool: xcpretty [xcpretty xcodebuild]
  output_dir: $BITRISE_DEPLOY_DIR
* artifact_name: ${scheme}
▼ is_export_xcarchive_zip: no [yes no]
▼ is_export_all_dsyms: no [yes no]
▼ verbose_log: no [yes no]

[app/pkg export configs]
▼ export_method: development [development app-store developer-id none]
  custom_export_options_plist_content: 

[xcodebuild configs]
* project_path: $BITRISE_PROJECT_PATH
* scheme: $BITRISE_SCHEME
  configuration: 
▼ is_clean_build: yes [yes no]
  workdir: $BITRISE_SOURCE_DIR


##############################################

* project_path: $BITRISE_PROJECT_PATH
* scheme: $BITRISE_SCHEME
  configuration: 
▼ export_method: development [development app-store developer-id none]

[Force Build Settings]
  force_team_id: 
  force_code_sign_identity: 
  force_provisioning_profile_specifier: 
  force_provisioning_profile: 

[Debug]
  custom_export_options_plist_content: 
* artifact_name: ${scheme}
  workdir: $BITRISE_SOURCE_DIR
  output_dir: $BITRISE_DEPLOY_DIR
▼ is_clean_build: yes [yes no]
▼ output_tool: xcpretty [xcpretty xcodebuild]
▼ is_export_xcarchive_zip: no [yes no]
▼ is_export_all_dsyms: no [yes no]
▼ verbose_log: no [yes no]

----------------------------------------------
----------------------------------------------

----------------------------------------------
bitrise-steplib/steps-xcode-test-mac:
----------------------------------------------

* project_path: $BITRISE_PROJECT_PATH
* scheme: $BITRISE_SCHEME
  destination: 
▼ is_clean_build: yes [yes no]
▼ generate_code_coverage_files: no [yes no]
▼ output_tool: xcpretty [xcpretty xcodebuild]
  workdir: $BITRISE_SOURCE_DIR


##############################################

* project_path: $BITRISE_PROJECT_PATH
* scheme: $BITRISE_SCHEME
  destination: 
▼ is_clean_build: yes [yes no]
▼ generate_code_coverage_files: no [yes no]
▼ output_tool: xcpretty [xcpretty xcodebuild]
  workdir: $BITRISE_SOURCE_DIR

no change
----------------------------------------------
----------------------------------------------

----------------------------------------------
bitrise-steplib/steps-cordova-archive:
----------------------------------------------

▼ platform: ios,android [ios,android ios android]
▼ configuration: release [release debug]
▼ target: device [device emulator]
  build_config: $BITRISE_CORDOVA_BUILD_CONFIGURATION
▼ readd_platform: true [true false]
  cordova_version: 
* workdir: $BITRISE_SOURCE_DIR
  options: 


##############################################

* workdir: $BITRISE_SOURCE_DIR
▼ platform: ios,android [ios,android ios android]
▼ configuration: release [release debug]
▼ target: device [device emulator]
  build_config: $BITRISE_CORDOVA_BUILD_CONFIGURATION
▼ readd_platform: true [true false]
  cordova_version: 
  options: 

----------------------------------------------
----------------------------------------------

----------------------------------------------
bitrise-steplib/steps-karma-jasmine-runner:
----------------------------------------------

* workdir: $BITRISE_SOURCE_DIR
* browsers: Safari
  options: 


##############################################

* workdir: $BITRISE_SOURCE_DIR
* browsers: Safari
  options: 

no change
----------------------------------------------
----------------------------------------------

----------------------------------------------
bitrise-steplib/steps-npm:
----------------------------------------------

  workdir: $BITRISE_SOURCE_DIR
* command: 


##############################################

* command: 
  workdir: $BITRISE_SOURCE_DIR


----------------------------------------------
----------------------------------------------
