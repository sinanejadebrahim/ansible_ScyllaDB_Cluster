# 🚀 ScyllaDB Cluster Ansible Role

Welcome to the **ScyllaDB Cluster Ansible Role**! This role automates the complex process of setting up a ScyllaDB cluster with the default configs needed, making it as simple as running a playbook. No extra configuration is needed beyond updating a few variables. Just run the role, and your cluster will be ready to go! 🎉

## 🌟 Features

- 📦 Installs Scylla Server
- ⚙️ Installs Scylla Manager Agent
- 🔧 Installs Scylla Manager
- 📋 Adds the cluster to Scylla Manager
- 🏁 Optionally initializes the cluster with:
  - 💽 Disk formatting
  - 🏎️ Running Scylla benchmarks
  - 🔧 Setting up necessary configurations
- 📦 Configures default settings for the cluster
- ✅ Tested on Ubuntu 22
- 🛠️ Zero additional configuration required!

## 📋 Prerequisites

Ensure the following prerequisites are met before running the role:

- 🐧 Ubuntu 22.04 LTS on target machines
- 🔐 SSH access to target machines

## 📁 Role Variables

Before running the role, review and update the variables in the `vars` file according to your environment and requirements. This step is crucial for the role to function correctly. Once set, you don't need to worry about any other configurations. 🎉

## 🚀 Usage

1. **Clone the repository** to your Ansible roles directory.

```bash
git clone https://github.com/sinanejadebrahim/ansible_ScyllaDB_Cluster.git
```

2. Update the Inventory.

```yaml
[db_hosts]
scylla_1 ansible_host=192.168.1.1
scylla_2 ansible_host=192.168.1.2
scylla_3 ansible_host=192.168.1.3
scylla_4 ansible_host=192.168.1.4
scylla_5 ansible_host=192.168.1.5

[management_host]
manager ansible_host=192.168.1.6
```

3. **Run the playbook**.

```bash
ansible-playbook -i inventory playbook.yml
```

## ✅ Verification

After the role completes, you can verify the cluster setup using the following commands:

- **On one of the Scylla nodes**:

```bash
nodetool status
```

- **On the Scylla Manager node**:

```bash
sctool cluster list
```

## 🤝 Contribution

Feel free to fork this repository and contribute by submitting pull requests. Any improvements or bug fixes are welcome! 🚀

## 📜 License

This project is licensed under the Apache License - see the [LICENSE](LICENSE) file for details.
