platform :osx, '10.13'
project 'BeardedSpice'

source 'https://github.com/CocoaPods/Specs.git'

target 'BeardedSpiceControllers' do
    pod 'MASShortcut', '~> 2.3.3'

    target 'BeardedSpice' do
        pod 'MASPreferences', '= 1.1.4'
        pod 'FMDB', '~> 2.6.2'

        # all pods for tests should ONLY go here
        target 'BeardedSpiceTests' do
            pod 'Kiwi'
            # pod 'OCMock'
            pod 'VCRURLConnection'
        end
    end
end

# Pods ship with ancient deployment targets (10.6+) that modern Xcode no longer
# supports (missing libarclite, warnings on arm64). Align them with the app.
post_install do |installer|
    installer.pods_project.targets.each do |target|
        target.build_configurations.each do |config|
            config.build_settings['MACOSX_DEPLOYMENT_TARGET'] = '10.13'
        end
    end
end
