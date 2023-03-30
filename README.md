# ssh_auth

This Ansible role manages the SSH daemon (SSHD) configuration on your servers. It allows you to define settings such as root login, password authentication, public key authentication, and challenge-response authentication.

## Requirements

This role requires Ansible 2.9 or higher. It is designed to work with SSHD on most Unix-based systems.

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

    sshd_config_file: The path to the SSHD configuration file (default: /etc/ssh/sshd_config).
    sshd_settings: A list of settings to be applied in the SSHD configuration file. The default settings are:
    PermitRootLogin: Allows root login (default: yes).
    PasswordAuthentication: Allows password authentication (default: yes).
    PubkeyAuthentication: Allows public key authentication (default: yes).
    ChallengeResponseAuthentication: Disables challenge-response authentication (default: no).

## Dependencies

None.

## Example Playbook

    - hosts: all
      roles:
      - role: sshd_config
          vars:
            sshd_settings:
              - name: PermitRootLogin
                value: "no"
              - name: PasswordAuthentication
                value: "no"
              - name: PubkeyAuthentication
                value: "yes"
              - name: ChallengeResponseAuthentication
                value: "no"

## License

This project is licensed under the MIT License.

## Author Information

This role was created in 2022 by Anthony Pagan.
