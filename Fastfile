# This file contains the fastlane.tools configuration
# You can find the documentation at https://docs.fastlane.tools
#
# For a list of all available actions, check out
#
#     https://docs.fastlane.tools/actions
#
# For a list of all available plugins, check out
#
#     https://docs.fastlane.tools/plugins/available-plugins
#

# Uncomment the line if you want fastlane to automatically update itself
# update_fastlane

default_platform(:ios)

platform :ios do
  desc "Description of what the lane does"
  lane :metrics do

    scan(scheme: "TestSonarApp",
      code_coverage: true,
      derived_data_path: "./DerivedData",
      output_directory: "./sonar-reports",
      devices: "iPhone 11 Pro Max")

    slather(cobertura_xml: true,
      jenkins: true,
      scheme: "TestSonarApp",
      build_directory: "./DerivedData",
      output_directory: "./sonar-reports",
      proj: "./TestSonarApp.xcodeproj")

     swiftlint(output_file: "./sonar-reports/swiftlint.txt",
      ignore_exit_status: true)

     sonar
end
end
