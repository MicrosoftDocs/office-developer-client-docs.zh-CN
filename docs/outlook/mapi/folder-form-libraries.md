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
  
在某些情况下，您可能希望将一个或多个窗体与特定文件夹关联。 例如，您组织的员工在个人邮件存储中可能都有一个"进度报告"文件夹，用于创建和存储进度报告。 由于进度报告特定于每个用户的进度报告文件夹，因此可能不适合将进度报告窗体存储在系统范围的表单库中。 但是，进度报告窗体的副本可以保存在每个用户的进度报告文件夹的关联内容表中。 这将限制用户在指定文件夹之外使用进度报告表单。
  
从概念上说，邮件存储中每个文件夹都有一个文件夹表单库，即使其中未安装任何表单服务器。 文件夹表单库的实现方式与其他表单库类似 ， 它们作为关联内容表存储在文件夹的备用部分。 由于文件夹窗体库包含在文件夹中，因此在复制操作中会与父文件夹一起复制它们。
  
## <a name="see-also"></a>另请参阅



[MAPI 表单](mapi-forms.md)

