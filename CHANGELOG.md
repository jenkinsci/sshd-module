Changelog
====

### 3.0

Release date: (Feb 22, 2021)

* [JENKINS-55582](https://issues.jenkins.io/browse/JENKINS-55582) Turn modules into plugins
* [JENKINS-55813](https://issues.jenkins.io/browse/JENKINS-55813) Ensure account status exceptions prevent successful SSH authentication

### 2.7

Release date: (Oct 12, 2020)

* [PR #35](https://github.com/jenkinsci/sshd-module/pull/35) - Make key exchange and MAC algorithms configurable via system properties, disable known obsolete algorithms by default.
* [PR #28](https://github.com/jenkinsci/sshd-module/pull/28), [PR #31](https://github.com/jenkinsci/sshd-module/pull/31), [PR #32](https://github.com/jenkinsci/sshd-module/pull/32) - Plugin modernization

### 2.6

Release date: (Feb 05, 2019)

* [JENKINS-55978](https://issues.jenkins-ci.org/browse/JENKINS-55978) -
SSHD Module did not apply a proper Apache Mina idle timeout value when a custom value was set by the 
`org.jenkinsci.main.modules.sshd.SSHD.idle-timeout` system property

### 2.5

Release date: (Nov 25, 2018)

* [JENKINS-45318](https://issues.jenkins-ci.org/browse/JENKINS-45318) -
Include the native EdDSA implementation into the module ([net.i2p.crypto:eddsa](https://github.com/str4d/ed25519-java)).

#### 2.4

Release date: (Feb 04, 2018)

* [PR #23](https://github.com/jenkinsci/sshd-module/pull/23) - 
Update SSHD Core from 1.6.0 to 1.7.0
([Full Changelog](https://issues.apache.org/jira/secure/ReleaseNote.jspa?version=12341097&styleName=Text&projectId=12310849&Create=Create&atl_token=A5KQ-2QAV-T4JA-FDED%7C47f5fd1e799680219ff14477b5b2c29ce7aaf6fd%7Clin))

#### 2.3

Release date: (Oct 27, 2017)

* [JENKINS-27026](https://issues.jenkins-ci.org/browse/JENKINS-27026) - 
Fire authentication events in [SecurityListener](https://jenkins.io/doc/developer/extensions/jenkins-core/#securitylistener)s when a user connects using SSH.
* [PR #21](https://github.com/jenkinsci/sshd-module/pull/21) -
Update Parent POM and resolve upper bound dependency issues.

#### 2.2

Release Date: (Oct 13, 2017)

* [#20](https://github.com/jenkinsci/sshd-module/pull/20) -
Make SSHD startup synchronous (partially reverts changes in 2.1). 

#### 2.1

Release Date: (September 25, 2017)

* [#19](https://github.com/jenkinsci/sshd-module/pull/19) - Do not wait for `SSHD` to be fully up during Jenkins startup.
* [#19](https://github.com/jenkinsci/sshd-module/pull/19) - Avoid race condition between `SSHD#start` and `SSHD#setPort`.

#### 2.0

Release Date: (July 05, 2017)

* Update from SSHD Core `0.14.0` to Apache MINA SSHD `1.6.0`
  * See links to the integrated changes below
* [JENKINS-43668](https://issues.jenkins-ci.org/browse/JENKINS-43668) - 
Cleanup [Trilead SSH-2](https://github.com/jenkinsci/trilead-ssh2) usages in the SSHD Module.
* [JENKINS-39738](https://issues.jenkins-ci.org/browse/JENKINS-39738) -
Enable `aes192ctr` and `aes256ctr` ciphers if JVM supports them (unlimited-strength encryption).

Integrated SSHD Changes:

* [SSHD 1.0.0](https://issues.apache.org/jira/secure/ReleaseNote.jspa?version=12323302&styleName=&projectId=12310849)
* [SSHD 1.1.0](https://issues.apache.org/jira/secure/ReleaseNote.jspa?version=12333293&styleName=&projectId=12310849)
* [SSHD 1.1.1](https://issues.apache.org/jira/secure/ReleaseNote.jspa?version=12335067&styleName=&projectId=12310849)
* [SSHD 1.2.0](https://issues.apache.org/jira/secure/ReleaseNote.jspa?version=12334702&styleName=&projectId=12310849)
* [SSHD 1.3.0](https://issues.apache.org/jira/secure/ReleaseNote.jspa?version=12335499&styleName=&projectId=12310849)
* [SSHD 1.4.0](https://issues.apache.org/jira/secure/ReleaseNote.jspa?version=12338322&styleName=&projectId=12310849)
* SSHD 1.5.0 - N/A, the release has been burned
* [SSHD 1.6.0](https://issues.apache.org/jira/secure/ReleaseNote.jspa?version=12340583&styleName=&projectId=12310849)

##### 2.0 Compatibility notice

* Plugins merely using the `SshCommandFactory` extension point to offer SSH services (`workflowLibs.git`, for example) should be unaffected.
* Plugins which referred to arbitrary `org.apache.sshd.**` classes may not work unless updated to use the `pluginFirstClassLoader` flag to bundle their own private copy in a fixed version
  * We do not see such plugins in https://github.com/jenkinsci and other public repositories

#### 1.11

Release date: (Apr 07, 2017) => Jenkins `2.54`

* [JENKINS-33595](https://issues.jenkins-ci.org/browse/JENKINS-33595) -
Disable SSHD port by default on new installations.

#### 1.10

Release date: (Mar 11, 2017) => Jenkins `2.51`

* [PR #9](https://github.com/jenkinsci/sshd-module/pull/9) - 
Move SSH server port configuration to security options page.

#### 1.9

Release date: (Dec 11, 2016) => Jenkins `2.37`, backported to `2.32.2`

* [PR #8](https://github.com/jenkinsci/sshd-module/pull/8) - 
Update SSHD Core from `0.8.0` to `0.14.0`.
* [JENKINS-40362](https://issues.jenkins-ci.org/browse/JENKINS-40362) -
SSHD Module: Handshake was failing (wrong shared secret) 1 out of 256 times due to 
[SSHD-330](https://issues.apache.org/jira/browse/SSHD-330).

Integrated SSHD Core Changes:

* [SSHD Core 0.9](https://issues.apache.org/jira/secure/ReleaseNote.jspa?projectId=12310849&version=12323301)
* [SSHD Core 0.10.0](https://issues.apache.org/jira/secure/ReleaseNote.jspa?projectId=12310849&version=12324784)
* [SSHD Core 0.10.1](https://issues.apache.org/jira/secure/ReleaseNote.jspa?projectId=12310849&version=12326289)
* [SSHD Core 0.11.0](https://issues.apache.org/jira/secure/ReleaseNote.jspa?projectId=12310849&version=12326277)
* [SSHD Core 0.12.0](https://issues.apache.org/jira/secure/ReleaseNote.jspa?projectId=12310849&version=12326775)
* [SSHD Core 0.13.0](https://issues.apache.org/jira/secure/ReleaseNote.jspa?projectId=12310849&version=12327342)
* [SSHD Core 0.14.0](https://issues.apache.org/jira/secure/ReleaseNote.jspa?projectId=12310849&version=12329012)

#### Previous

There is no changelogs for this release and previous ones. 
See the commit history.
