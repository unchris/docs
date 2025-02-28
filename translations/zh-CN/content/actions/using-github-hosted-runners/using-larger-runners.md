---
title: 使用较大运行器
shortTitle: Larger runners
intro: '{% data variables.product.prodname_dotcom %} 提供具有更多 RAM 和 CPU 的较大运行器。'
miniTocMaxHeadingLevel: 3
product: '{% data reusables.gated-features.hosted-runners %}'
versions:
  feature: actions-hosted-runners
ms.openlocfilehash: eca33ee8b427f918a3db5d8b4ca05947b7662896
ms.sourcegitcommit: d0cea547f6a5d991a28c310257cafd616235889f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/01/2022
ms.locfileid: '148120871'
---
## {% data variables.actions.hosted_runner %} 概述

除了 [标准 {% data variables.product.prodname_dotcom %} 托管的运行器](/actions/using-github-hosted-runners/about-github-hosted-runners#supported-runners-and-hardware-resources)之外，{% data variables.product.prodname_dotcom %} 还在 {% data variables.product.prodname_team %} 和 {% data variables.product.prodname_ghe_cloud %} 计划中为客户提供一系列具有更多 RAM 和 CPU 的 {% data variables.actions.hosted_runner %}。 这些运行器由 {% data variables.product.prodname_dotcom %} 托管，并预安装了运行器应用程序和其他工具。

为组织启用{% data variables.actions.hosted_runner %}时，将自动为你创建一个默认运行器组，其中包含四个预配置的{% data variables.actions.hosted_runner %}。

向组织添加 {% data variables.actions.hosted_runner %} 时，会通过精选的可用硬件规范和操作系统映像定义计算机类型。 {% data variables.product.prodname_dotcom %} 随后会创建此运行器的多个实例，这些实例可基于定义的自动缩放限制，纵向扩展和缩减以匹配组织的作业需求。

## {% data variables.actions.hosted_runner %} 的计算机规格 

|大小 (vcpu) | 内存 (GB) | 存储 (SSD) |
| ------------- | ------------- | ------------- |
|4 核 | 16 RAM  | 150 GB|
| 8 核 | 32 RAM | 300 GB |
|16 核| 64 RAM | 600 GB |
|32 个核心| 128 RAM| 1200 GB|
|64 个核心| 256 RAM | 2040 GB|

## {% data variables.actions.hosted_runner %} 体系结构概述

{% data variables.actions.hosted_runner %} 在组织级别进行管理，它们被安排为可以包含运行器的多个实例的各个组。 它们还可以在企业级别进行创建，并与层次结构中的组织共享。 创建组后，可向组添加运行器并更新工作流，将组名或分配给 {% data variables.actions.hosted_runner %} 的标签作为目标。 还可以控制允许哪些存储库将作业发送到组进行处理。 有关组的详细信息，请参阅“[控制对 {% data variables.actions.hosted_runner %} 的访问](/actions/using-github-hosted-runners/controlling-access-to-larger-runners)”。

在下图中，使用自定义硬件和操作系统配置定义了名为 `ubuntu-20.04-16core` 的托管运行器类别。

![说明 {% data variables.actions.hosted_runner %} 的关系图](/assets/images/hosted-runner.png)

1. 此运行器的实例会自动创建并添加到名为 `grp-ubuntu-20.04-16core` 的组。 
2. 运行器已分配有标签 `ubuntu-20.04-16core`。 
3. 工作流作业在其 `runs-on` 键中使用 `ubuntu-20.04-16core` 标签来指示执行作业所需的运行器类型。
4. {% data variables.product.prodname_actions %} 会检查运行器组，以查看是否授权存储库将作业发送到运行器。
5. 作业在 `ubuntu-20.04-16core` 运行器的下一个可用实例上运行。

## {% data variables.actions.hosted_runner %} 的自动缩放

{% data variables.actions.hosted_runner %} 可以配置为自动缩放以满足需求。 提交作业进行处理时，可以自动预配更多计算机以运行作业，直到达到预定义的最大限制。 每台计算机一次只处理一个作业，因此这些设置实际上确定可以并发运行的作业数。 

在运行器部署过程中，可以配置“最大值”选项，这使你可以通过设置在此集中创建的最大并行计算机数来控制成本。 此处的较高值可帮助避免由于并行而阻止工作流。

## {% data variables.actions.hosted_runner %} 的网络

默认情况下，{% data variables.actions.hosted_runner %} 会接收为每个作业运行而更改的动态 IP 地址。 （可选）{% data variables.product.prodname_ghe_cloud %} 客户可以将其 {% data variables.actions.hosted_runner %} 配置为从 {% data variables.product.prodname_dotcom %} 的 IP 地址池接收静态 IP 地址。 启用后，{% data variables.actions.hosted_runner %} 的实例会从对运行器唯一的范围接收地址，从而使你能够使用此范围配置防火墙允许列表。 {% ifversion fpt %}在你所有的{% data variables.actions.hosted_runner %}中，最多可以使用 10 个静态 IP 地址范围{% endif %}{% ifversion ghec %}对于在企业级别创建的{% data variables.actions.hosted_runner %}，最多可以使用 10 个静态 IP 地址范围。 此外，对于在组织级别为企业中的每个组织创建的{% data variables.actions.hosted_runner %}，最多可以使用 10 个静态 IP 地址范围{% endif %}。

{% note %}

注意：如果运行器未使用的时间超过 30 天，则其 IP 地址范围会自动移除，无法恢复。

{% endnote %}

## {% data variables.actions.hosted_runner %} 的规划

### 创建运行器组

运行器组用于收集虚拟机集，并围绕它们创建安全边界。 随后可以确定允许哪些组织或存储库在这些计算机集上运行作业。 在 {% data variables.actions.hosted_runner %} 部署过程中，运行器可以添加到现有组，否则会加入默认组。 可以按照“[控制对 {% data variables.actions.hosted_runner %} 的访问](/actions/using-github-hosted-runners/controlling-access-to-larger-runners)”中的步骤创建组。

### 了解计费

{% note %}

注意：{% data variables.actions.hosted_runner %}不使用包含的权利分钟数，并且针对公共存储库不是免费的。

{% endnote %}

与标准 {% data variables.product.prodname_dotcom %} 托管的运行器相比，{% data variables.actions.hosted_runner %} 的计费方式有所不同。 有关详细信息，请参阅“[每分钟费率](/billing/managing-billing-for-github-actions/about-billing-for-github-actions#per-minute-rates)”。

## 将 {% data variables.actions.hosted_runner %} 添加到企业

可以将 {% data variables.actions.hosted_runner %} 添加到企业，在该企业中可以将它们分配给多个组织。 组织管理员随后可以控制哪些存储库可以使用运行器。 若要将 {% data variables.actions.hosted_runner %} 添加到企业，你必须是组织所有者。

{% data reusables.actions.add-hosted-runner-overview %}

{% data reusables.enterprise-accounts.access-enterprise %} {% data reusables.enterprise-accounts.policies-tab %} {% data reusables.enterprise-accounts.actions-tab %} {% data reusables.enterprise-accounts.actions-runners-tab %} {% data reusables.actions.add-hosted-runner %}
1. 若要允许组织访问 {% data variables.actions.hosted_runner %}，请指定可以使用它的组织列表。 有关详细信息，请参阅“[管理对运行器的访问](#managing-access-to-your-runners)”。

## 将 {% data variables.actions.hosted_runner %} 添加到组织

可以将 {% data variables.actions.hosted_runner %} 添加到组织，其中的组织管理员可以控制哪些存储库可以使用它。 

{% data reusables.actions.add-hosted-runner-overview %}

{% data reusables.organizations.navigate-to-org %} {% data reusables.organizations.org_settings %} {% data reusables.organizations.settings-sidebar-actions-runners %} {% data reusables.actions.add-hosted-runner %}
1. 若要允许存储库访问 {% data variables.actions.hosted_runner %}，请将它们添加到可以使用它的存储库列表中。 有关详细信息，请参阅“[管理对运行器的访问](#managing-access-to-your-runners)”。

## 在运行器上运行作业

定义了运行器类型后，可以更新工作流 YAML 文件，以将作业发送到新创建的运行器实例进行处理。 可使用运行器组或标签来定义作业的运行位置。 

只有所有者或管理员帐户可查看运行器设置。 非管理用户可联系组织管理员，了解启用了哪些运行器。 组织管理员可创建新的运行器和运行器组，并配置权限来指定哪些存储库可访问运行器组。

### 使用组来控制作业的运行位置

{% data reusables.actions.jobs.example-runs-on-groups %}

### 使用标签来控制作业的运行位置

在此示例中，使用 Ubuntu 16 核运行器填充运行器组，这些运行器也分配有标签 `ubuntu-20.04-16core`。 `runs-on` 键将作业发送至具有匹配标签的任何可用运行器：

```yaml
name: learn-github-actions
on: [push]
jobs:
  check-bats-version:
    runs-on:
      labels: ubuntu-20.04-16core
    steps:
      - uses: {% data reusables.actions.action-checkout %}
      - uses: {% data reusables.actions.action-setup-node %}
        with:
          node-version: '14'
      - run: npm install -g bats
      - run: bats -v
```

### 使用组和组来控制作业的运行位置

{% data reusables.actions.jobs.example-runs-on-labels-and-groups %}

### 使用多个标签

可指定要使作业在运行器上运行而需要匹配的多个标签。 运行器将需要匹配所有标签才能运行该作业。

在此示例中，运行器将需要匹配全部三个标签才能运行作业：

```yaml
name: learn-github-actions
on: [push]
jobs:
  check-bats-version:
    runs-on:
      labels: [ ubuntu-20.04-16core, gpu, qa ]
    steps:
      - uses: {% data reusables.actions.action-checkout %}
      - uses: {% data reusables.actions.action-setup-node %}
        with:
          node-version: '14'
      - run: npm install -g bats
      - run: bats -v
```

{% data reusables.actions.section-using-unique-names-for-runner-groups %}

## 管理对运行器的访问

{% note %}

注意：必须先为运行器组配置权限，然后工作流才能将作业发送到 {% data variables.actions.hosted_runner %}。 有关详细信息，请参阅下列各节。

{% endnote %}

运行器组用于控制哪些存储库可以在 {% data variables.actions.hosted_runner %} 上运行作业。 必须从管理层次结构的各个级别授予对组的访问权限，具体取决于定义 {% data variables.actions.hosted_runner %} 的位置：

- 企业级别的运行器：配置运行器组以授予对所有所需组织的访问权限。 此外，对于每个组织，必须配置组以指定允许访问的存储库。
- 组织级别的运行器：通过指定允许访问的存储库来配置运行器组。

例如，下图包含一个企业级别的名为 `grp-ubuntu-20.04-16core` 的运行器组。 在名为 `octo-repo` 的存储库可以使用该组中的运行器之前，必须先在企业级别配置该组以允许从 `octo-org` 组织进行访问；随后必须在组织级别配置该组以允许从 `octo-repo` 进行访问：

![说明 {% data variables.actions.hosted_runner %} 组的关系图](/assets/images/hosted-runner-mgmt.png)

### 允许存储库访问运行器组

此过程演示如何在企业和组织级别配置组权限：

{% data reusables.actions.runner-groups-navigate-to-repo-org-enterprise %} {% data reusables.actions.settings-sidebar-actions-runner-groups-selection %}
  - 对于企业中的运行器组：在“组织访问”下，修改可以访问运行器组的组织。
  - 对于组织中的运行器组：在“存储库访问”下，修改可以访问运行器组的存储库。

{% warning %}

**警告**：

{% data reusables.actions.hosted-runner-security %}

有关详细信息，请参阅“[控制对 {% data variables.actions.hosted_runner %} 的访问](/actions/using-github-hosted-runners/controlling-access-to-larger-runners)”。

{% endwarning %}
