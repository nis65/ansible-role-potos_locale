
# Ansible Role - potos\_locale

This role works for me, but does not satisfy the potos acceptance rules yet:

* the automated checks are currently failing
* meta is not up to date

Role to set the systemwide `LANG` in `/etc/default/locale`.
Ensures that the relevant locale is generated. Furthermore,
it allows to install arbitrary packages via apt. It is
recommended to use it for language specific packages only.

## Example Playbook

As this role is tested via Molecule one can use [that
playbook](./molecule/default/converge.yml) as a starting point:

```yaml
---

- name: Converge
  hosts: all
  gather_facts: yes
  tasks:
    - name: run role
      ansible.builtin.include_role:
        name: 'ansible-role-potos_template'
```

## Role Variables

The default variables are defined in [defaults/main.yml](./defaults/main.yml):

```yaml
---

potos_locale_lang: "de_CH.UTF-8"
potos_locale_pkgs:
  - language-pack-gnome-de-base
```

Another option is to use `ansible-doc` to read the argument specification:

```sh
ansible-doc --type role -r . main ansible-role-potos_template
```

## Requirements

N/A

## License

See [LICENSE](./LICENSE)

## Author Information

[Project Potos](https://github.com/projectpotos)

