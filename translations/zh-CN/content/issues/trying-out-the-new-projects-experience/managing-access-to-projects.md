---
title: 管理对项目的访问（测试版）
intro: 您可以控制谁可以查看、编辑或管理您的项目。
allowTitleToDifferFromFilename: true
miniTocMaxHeadingLevel: 2
versions:
  fpt: '*'
  ghec: '*'
topics:
- Projects
- Organizations
ms.openlocfilehash: 2c50343bfe8e3fd4e65a9a39b798f355cf0f13bb
ms.sourcegitcommit: 22d665055b1bee7a5df630385e734e3a149fc720
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/13/2022
ms.locfileid: "145128671"
---
{% data reusables.projects.projects-beta %}

## <a name="about-project-access"></a>关于项目访问

组织级项目的管理员可以管理整个组织、团队、单个组织成员和外部协作者的访问权限。 

用户级项目的管理员可以邀请单个协作者并管理其访问权限。

项目管理员还可以控制其项目在互联网上对每个人的可见性。 有关详细信息，请参阅“[管理项目的可见性](/issues/trying-out-the-new-projects-experience/managing-the-visibility-of-your-projects)”。

## <a name="managing-access-for-organization-level-projects"></a>管理组织级项目的访问权限

### <a name="managing-access-for-everyone-in-your-organization"></a>管理组织中每个人的访问权限

默认的基本角色是 `write`，这意味着组织中的每个人都可以查看和编辑项目。 要更改组织中每个人的项目访问权限，您可以更改基本角色。 对基本角色的更改仅影响不是组织所有者且未被授予个人访问权限的组织成员。

{% data reusables.projects.project-settings %}
1. 单击“管理访问”。
2. 在“基本角色”下，选择默认角色。
   - 无访问权限：只有组织所有者和被授予个人访问权限的用户才能查看该项目。 组织所有者也是项目的管理员。
   - 读取：组织中的每个人都可以查看项目。 组织所有者也是项目的管理员。
   - 写入：组织中的每个人都可以查看并编辑项目。 组织所有者也是项目的管理员。
   - 管理员：组织中的每个人都是项目的管理员。

### <a name="managing-access-for-teams-and-individual-members-of-your-organization"></a>管理组织中团队和单个成员的访问权限

您还可以将团队、外部协作者和单个组织成员添加为组织级项目的协作者。 有关详细信息，请参阅“[关于团队](/organizations/organizing-members-into-teams/about-teams)”。

仅当单个用户已经是组织中的成员或组织中至少一个存储库的外部协作者时，您才能邀请该用户协作处理组织级项目。

{% data reusables.projects.project-settings %}
1. 单击“管理访问”。
2. 在“邀请协作者”下，搜索要邀请的团队或单个用户。
3. 为协作者选择角色。
   - 读取：团队或个人可以查看项目。
   - 写入：团队或个人可以查看和编辑项目。
   - 管理员：团队或个人可以查看、编辑项目，还可为项目添加新协作者。
4. 单击“邀请”。 

### <a name="managing-access-of-an-existing-collaborator-on-your-project"></a>管理现有协作者对项目的访问

{% data reusables.projects.project-settings %}
1. 单击“管理访问”。
1. 在“管理访问权限”下，找到要修改其权限的协作者。

   可以使用“类型”和“角色”下拉菜单来筛选访问列表 。

1. 编辑协作者的角色，或单击 {% octicon "trash" aria-label="the trash icon" %} 以删除协作者。

## <a name="managing-access-for-user-level-projects"></a>管理用户级项目的访问权限

### <a name="granting-a-collaborator-access-to-your-project"></a>授予协作者对项目的访问权限

{% note %}

这只会影响项目的协作者，而不会影响项目中的存储库。 要查看项目上的项，必须具有该项所属存储库所需的权限。 如果项目包含私有存储库中的项目，则不是存储库协作者的用户将无法查看该存储库中的项。 有关详细信息，请参阅“[设置存储库可见性](/repositories/managing-your-repositorys-settings-and-features/managing-repository-settings/setting-repository-visibility)”和“[管理有权访问存储库的团队和人员](/repositories/managing-your-repositorys-settings-and-features/managing-repository-settings/managing-teams-and-people-with-access-to-your-repository)”。

{% endnote %}

{% data reusables.projects.project-settings %}
1. 单击“管理访问”。
2. 在“邀请协作者”下，搜索要邀请的用户。
3. 为协作者选择角色。
   - 读取：个人可以查看项目。
   - 写入：个人可以查看和编辑项目。
   - 管理员：个人可以查看、编辑项目，还可为项目添加新协作者。
4. 单击“邀请”。 

### <a name="managing-access-of-an-existing-collaborator-on-your-project"></a>管理现有协作者对项目的访问

{% data reusables.projects.project-settings %}
1. 单击“管理访问”。
1. 在“管理访问权限”下，找到要修改其权限的协作者。

   可以使用“角色”下拉菜单来筛选访问列表。

1. 编辑协作者的角色，或单击 {% octicon "trash" aria-label="the trash icon" %} 以删除协作者。
