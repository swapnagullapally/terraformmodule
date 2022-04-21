# Terraform Coding Exercise

Please read the [instructions](./INSTRUCTIONS.md) file.

Instructions to test this:
   1. Clone this code to your local environment 
   2. navigate to terraformmodule/examples/exercise/  and run " Terraform Init "  
   3. Then run " Terraform Plan " 
   4. run "Terraform Apply"

=============================================================
Output would be like below:
==========================================================

[root@ip-172-31-85-143 exercise]# terraform apply

Terraform used the selected providers to generate the following execution plan. Resource actions are indicated with the following symbols:
  + create

Terraform will perform the following actions:

  # module.dns_updater.dns_a_record_set.www[0] will be created
  + resource "dns_a_record_set" "www" {
      + addresses = [
          + "192.168.100.1",
        ]
      + id        = (known after apply)
      + name      = "www"
      + ttl       = 60
      + zone      = "example.com."
    }

  # module.dns_updater.dns_a_record_set.www[1] will be created
  + resource "dns_a_record_set" "www" {
      + addresses = [
          + "192.168.100.1",
        ]
      + id        = (known after apply)
      + name      = "www"
      + ttl       = 600
      + zone      = "example.com."
    }

  # module.dns_updater.dns_a_record_set.www[2] will be created
  + resource "dns_a_record_set" "www" {
      + addresses = [
          + "1.1.1.1",
        ]
      + id        = (known after apply)
      + name      = "www"
      + ttl       = 300
      + zone      = "example.com."
    }

Plan: 3 to add, 0 to change, 0 to destroy.

Do you want to perform these actions?
  Terraform will perform the actions described above.
  Only 'yes' will be accepted to approve.

  Enter a value: yes

module.dns_updater.dns_a_record_set.www[1]: Creating...
module.dns_updater.dns_a_record_set.www[2]: Creating...
module.dns_updater.dns_a_record_set.www[0]: Creating...
module.dns_updater.dns_a_record_set.www[0]: Creation complete after 0s [id=www.example.com.]
module.dns_updater.dns_a_record_set.www[1]: Creation complete after 0s [id=www.example.com.]
module.dns_updater.dns_a_record_set.www[2]: Creation complete after 0s [id=www.example.com.]

Apply complete! Resources: 3 added, 0 changed, 0 destroyed.
[root@ip-172-31-85-143 exercise]# terraform show

# module.dns_updater.dns_a_record_set.www[0]:
resource "dns_a_record_set" "www" {
    addresses = [
        "192.168.100.1",
    ]
    id        = "www.example.com."
    name      = "www"
    ttl       = 300
    zone      = "example.com."
}

# module.dns_updater.dns_a_record_set.www[1]:
resource "dns_a_record_set" "www" {
    addresses = [
        "192.168.100.1",
    ]
    id        = "www.example.com."
    name      = "www"
    ttl       = 300
    zone      = "example.com."
}

# module.dns_updater.dns_a_record_set.www[2]:
resource "dns_a_record_set" "www" {
    addresses = [
        "1.1.1.1",
    ]
    id        = "www.example.com."
    name      = "www"
    ttl       = 300
    zone      = "example.com."
}
