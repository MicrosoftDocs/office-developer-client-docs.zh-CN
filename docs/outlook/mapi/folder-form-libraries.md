---
title: 文件夹表单库
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 62b7480e-b3eb-45fb-b74d-62f1dc918a53
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: ec12cf567dbbd8c1710f835a3c19369dd3626fd4
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33414282"
---
# <a name="folder-form-libraries"></a>文件夹表单库

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
在某些情况下, 您可能需要将一个或多个表单与特定文件夹相关联。 例如, 组织中的员工都可以在其个人邮件存储中拥有一个进度报告文件夹, 用于创建和存储进度报告。 由于进度报告是特定于每个用户的进度报告文件夹的, 因此在系统范围的表单库中存储进度报告表单可能不合适。 但是, 可以将进度报告表单的副本保存在每个用户的 "进度报告" 文件夹的 "相关内容" 表中。 这将限制用户在指定的文件夹之外使用进度报告表单。
  
从概念上讲, 邮件存储区中的每个文件夹都有一个 "文件夹表单库", 即使其中未安装表单服务器也是如此。 文件夹表单库的实现方式与其他表单库一样, 它们在文件夹的备用部分中存储为关联表。 由于文件夹表单库包含在文件夹中, 因此它们会在复制操作中与其父文件夹一起复制。
  
## <a name="see-also"></a>另请参阅



[MAPI 表单](mapi-forms.md)

