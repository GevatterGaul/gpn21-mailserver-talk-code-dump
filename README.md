# GPN21 Mailserver Talk Code Dump

This is the example code used in the GPN21 Mailserver Talk.

Caution: this is demo code and not intended for production use. Several important parts of a mailserver are missing, like backup, firewall, update mechanism, SPF, DMARC and others.

Caution2: this is an unmaintained dump.

## VM Setup

To use a demo vm on azure, first [set up your Azure environment](https://boredconsultant.com/2022/03/02/Azure-VM-Deployment-With-Ansible/). Then put your ssh pubkey into start-mailser.yml and set your desired DNS prefix.

Start the VM like this:

```bash
ansible-playbook start-mailer.yml
```

## Mailer Setup

Adapt `hosts.yml` to fit your vm domain. Change all occurences of my fun domain `molybdaen4men.de` to your actual domain. Do not forget the DNS entries and the MX entry.

Every part of the mailserver has a separate playbook so that it can be started easily during the demo. To set up all parts at once:

```bash
ansible-playbook mailer.yml
```

## Further Reading

You can find in depth explanations of the mailserver components here: https://boredconsultant.com/tags/mailserver/
