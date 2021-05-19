---
title: 个人表单库
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 6ffcd93c-3737-4342-9cd0-2ca7c0fba52c
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: c84665077f9c8e02647a4d348042515366b0c090
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33420407"
---
# <a name="personal-form-libraries"></a>个人表单库

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
正如其名称所示，个人表单库包含特定用户感兴趣的表单。 用户的个人表单库是与该用户配置文件中标识的默认邮件存储关联的表单库;工作站上安装的每个配置文件都可以使用单独的默认存储，因此可以使用单独的个人表单库。 个人表单库可以包含除其他表单外还包含在其他表单库中的表单的副本。
  
个人表单库在用户默认邮件存储中根文件夹的关联内容表中实现， 无论是驻留在服务器上还是本地用户工作站上，都是不重要的。 如果用户的默认邮件存储存储在用户工作站上，则个人表单库通过允许应用程序在本地而不是网络访问表单来提高性能。 它还使脱机工作的用户能够使用表单，当用户希望将其表单放在便携计算机上并且无法访问网络时，可能发生此情况。
  
个人表单库项的属性和基础实现包括一个"容器 ID"属性，该属性标识必须与本地条目同步的主容器。 这可以是包含窗体的任意文件夹的标识符。 如果使用的是支持某种组织范围的表单库的自定义表单管理器，这将非常有用;表单管理器将负责同步存储在个人表单库和组织范围的表单库中的表单。 加载表单管理器时可能会发生这种情况，但理论上可能随时发生。
  
## <a name="see-also"></a>另请参阅



[MAPI 表单](mapi-forms.md)

