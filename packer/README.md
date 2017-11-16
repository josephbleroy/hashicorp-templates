# Packer

Create baseline machine images using code. 

### Supported Platforms

Build images for almost every operating system and every major cloud provider, virtual machine platform, and container environment. 

Supports the following: 

- Linux
- Microsoft Windows
- Mac OS X
- Docker
- VirtualBox
- VMware
- AWS
- GCP
- Azure

Along with many others.

### Why Use Packer

Helps prevent misconfigurations and allows you to create pipelines for building and deploying images. 

Helps prevent configuration drift when updating software packages and making applying security patches.

It helps you keep your entire infrastrucutre environment consistent. When you need to patch something, you make the updates in testing environment, check to make sure it works, and then rebuild your production environment with the working image build. 

### Building Images

You use a base image, such as an AMI or ISO, and then install packages and configure them to build a more customized image. You can also uninstall packages, make system configuration changes, etc., before creating the final image.

To build an image, run the following:

`make virtualbox` or `make aws`

### Custom Provisioning

You can add any package that you wish to install in the `scripts/provision.sh` file.

### Key Terms

Pretty useful to remember what these terms mean. 

- Template: specify all the details of how you want the final image to look like. 
- Artifacts: output from the image build.
- Builders: turns a template into a machine and then into an image.
- Communicators: communicate with the remote hosts (such as AWS) using SSH or WinRM. 
- Post Processors: output the image to a pipeline. For example, when you build a container image in Docker, you can also send it to Docker Hub and keep it within that ecosystem.

### Accessing Vagrant Box

Run `vagrant up --provider=virtualbox` if you want to start the newly created virtual machine using Vagrant.

To access the virtual machine, you can SSH in using the following command:

`ssh - p 2222 vagrant@192.168.53.3 ~/.vagrant.d/insecure_private_key`

### Policy

```
{
  "Version": "2012-10-17",
  "Statement": [{
      "Effect": "Allow",
      "Action" : [
        "ec2:AttachVolume",
        "ec2:AuthorizeSecurityGroupIngress",
        "ec2:CopyImage",
        "ec2:CreateImage",
        "ec2:CreateKeypair",
        "ec2:CreateSecurityGroup",
        "ec2:CreateSnapshot",
        "ec2:CreateTags",
        "ec2:CreateVolume",
        "ec2:DeleteKeypair",
        "ec2:DeleteSecurityGroup",
        "ec2:DeleteSnapshot",
        "ec2:DeleteVolume",
        "ec2:DeregisterImage",
        "ec2:DescribeImageAttribute",
        "ec2:DescribeImages",
        "ec2:DescribeInstances",
        "ec2:DescribeRegions",
        "ec2:DescribeSecurityGroups",
        "ec2:DescribeSnapshots",
        "ec2:DescribeSubnets",
        "ec2:DescribeTags",
        "ec2:DescribeVolumes",
        "ec2:DetachVolume",
        "ec2:GetPasswordData",
        "ec2:ModifyImageAttribute",
        "ec2:ModifyInstanceAttribute",
        "ec2:ModifySnapshotAttribute",
        "ec2:RegisterImage",
        "ec2:RunInstances",
        "ec2:StopInstances",
        "ec2:TerminateInstances"
      ],
      "Resource" : "*"
  }]
}
```

### Resources 

http://www.hashbangcode.com/blog/connecting-vagrant-box-without-vagrant-ssh-command







