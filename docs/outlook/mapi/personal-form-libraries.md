---
title: 个人表单库
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 6ffcd93c-3737-4342-9cd0-2ca7c0fba52c
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 0793fefd744eecc95899c4166cb8a1a6a2e6cd2f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776589"
---
# <a name="personal-form-libraries"></a>个人表单库

  
  
**适用于**： Outlook 
  
顾名思义，个人窗体库包含关注某个特定用户的窗的体。 用户的个人窗体库是与默认的邮件存储中的用户配置文件; 标识关联的表单库每个工作站上安装的配置文件可以使用不同的默认存储区，因此，一个单独的个人窗体库。 个人窗体库可以包含还包含其他除了其他窗体的窗体库中的窗体的副本。
  
在用户的默认邮件存储区中的根文件夹的相关内容表中实现的个人窗体库 — 的驻留在服务器或本地用户的工作站上并不重要。 如果用户的工作站上存储用户的默认邮件存储区，个人窗体库使应用程序能够通过网络访问形式而不是本地提供增强的性能。 它还使窗体可供脱机工作时用户希望采用其与他们便携式计算机上的形式可能发生，同时无须访问网络的用户。
  
属性和基础实现个人窗体库项包括"容器 ID"属性，用于标识必须与同步本地条目的主容器。 这可以是任意文件夹包含表单的标识符。 这很有用，如果您使用的支持组织范围内表单库; 某种自定义窗体管理器窗体管理器将负责同步个人窗体库和组织范围内窗体库中存储的表单。 窗体管理器已加载，但无法在任何时候理论上发生时，可能会发生这种情况。
  
## <a name="see-also"></a>另请参阅



[MAPI 表单](mapi-forms.md)

