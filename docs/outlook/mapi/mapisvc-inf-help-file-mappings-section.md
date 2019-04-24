---
title: mapisvc.inf [帮助文件映射] 部分
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 62aee641-b73f-4f53-9e8d-adf010c9ea1a
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 4760c9965975bb5d950e51b707d28bee647ef99a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32269970"
---
# <a name="mapisvcinf-help-file-mappings-section"></a>mapisvc.inf [帮助文件映射] 部分

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
**[帮助文件映射]** 部分包含的条目分别对应于为该服务生成的错误提供帮助的文件中的一条邮件服务。 此部分中的条目使用以下格式: 
  
 **[帮助文件映射]**_邮件服务名称_ =  _帮助文件名_
  
邮件服务名称是已安装的邮件服务的名称;帮助文件名是错误信息所在的文件的名称。 下面的示例显示了一个典型的 **[帮助文件映射]** 部分, 其中包含三个服务的条目: MAPI、MsgService 服务和 MS service。 
  
```cpp
[Help File Mappings]
MAPI=MAPI.HLP
MsgService=MYHELP.HLP
MS=STORE.HLP

```


