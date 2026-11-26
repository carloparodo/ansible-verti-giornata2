# Ansible Verti - Giornata 2 (AAP-only)

Repository didattico per i laboratori della Giornata 2.

## Perche AAP-only
I corsisti non devono accedere direttamente al repository: AAP sincronizza questo repository in un Project e i Job Template selezionano i playbook dalla tendina **Playbook**.

## Project AAP
- Name: `LAB-D2-Ansible`
- Organization: `Verti`
- Source control type: `Git`
- Source control URL: URL pubblico di questo repository
- Source control credential: nessuna, se il repository e pubblico
- Execution Environment: `EE Supported Quay`

## Percorso dei corsisti
Ogni partecipante mantiene il proprio Inventory `LAB-D1-P1` ... `LAB-D1-P4` e il proprio Job Template `LAB-D2-P1` ... `LAB-D2-P4`. Per passare a un laboratorio successivo cambia soltanto il campo **Playbook** del proprio Job Template e, quando richiesto, le **Extra Variables**.

## Playbook core
1. `playbooks/lab01_first_run.yml`
2. `playbooks/lab02_file_copy.yml`
3. `playbooks/lab03_group_user.yml`
4. `playbooks/lab04_httpd_service_uri.yml`
5. `playbooks/lab05_extra_vars.yml`
6. `playbooks/lab06_facts_when.yml`
7. `playbooks/lab07_register_command.yml`
8. `playbooks/lab08_loop.yml`
9. `playbooks/lab09_shell_multicheck.yml`
10. `playbooks/lab10_integrated_baseline.yml`

## Riserva didattica
- `bonus01_variables_matrix.yml`
- `bonus02_controlled_failure.yml`
- `bonus03_check_diff.yml`
- `bonus04_troubleshooting.yml`

## Variabili utili
Esempio da inserire nelle Extra Variables del Job Template:

```yaml
lab_root: /tmp/ansible_d2
environment: test
application_port: 8080
lab_message: Primo messaggio dal Job Template
lab_package: httpd
lab_service: httpd
```

Per `lab08_loop.yml`:

```yaml
lab_dirs:
  - config
  - data
  - logs
```

## Nota di sicurezza
Gli esercizi sono pensati per le VM dedicate del laboratorio. Non eseguire questi playbook su host aziendali diversi dalle VM assegnate ai corsisti. Lo snapshot/revert, se necessario, resta a cura del personale Verti.
