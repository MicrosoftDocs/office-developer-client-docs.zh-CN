---
title: MapiSvc.inf [Help File Mappings] Section
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 62aee641-b73f-4f53-9e8d-adf010c9ea1a
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 4760c9965975bb5d950e51b707d28bee647ef99a
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33407555"
---
# <a name="mapisvcinf-help-file-mappings-section"></a>MapiSvc.inf [Help File Mappings] Section

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
**[帮助文件映射]** 部分包含条目，每个条目将一个邮件服务映射到文件，该文件为服务生成的错误提供帮助。 本节中的条目使用以下格式： 
  
 **[帮助文件映射]** _邮件服务名称_  =   _帮助文件名_
  
邮件服务名称是已安装的邮件服务的名称;帮助文件名是错误信息所在的文件的名称。 以下示例显示了一个典型的 **[帮助** 文件映射] 部分，其中包含三个服务的条目：MAPI、MsgService 服务和 MS 服务。 
  
```cpp
[Help File Mappings]
MAPI=MAPI.HLP
MsgService=MYHELP.HLP
MS=STORE.HLP

```


