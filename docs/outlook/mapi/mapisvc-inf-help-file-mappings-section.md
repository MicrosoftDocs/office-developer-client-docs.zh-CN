---
title: MapiSvc.inf [帮助文件映射] 部分
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 62aee641-b73f-4f53-9e8d-adf010c9ea1a
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 776f797d0c96d9173e114fd499d6cca0494a0a43
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776403"
---
# <a name="mapisvcinf-help-file-mappings-section"></a>MapiSvc.inf [帮助文件映射] 部分

  
  
**适用于**： Outlook 
  
**[帮助文件映射]** 节中包含每个将一个邮件服务映射到提供有关服务所生成的错误的帮助文件的项。 本节中的项使用以下格式： 
  
 **[帮助文件映射]**_消息服务名称_ =  _帮助文件名_
  
消息服务名称是已安装的邮件服务; 的名称帮助文件名称为错误信息所在的文件的名称。 下面的示例显示了一个典型的 **[帮助文件映射]** 节包含三种服务的条目： MAPI，MsgService 服务和 MS 服务。 
  
```cpp
[Help File Mappings]
MAPI=MAPI.HLP
MsgService=MYHELP.HLP
MS=STORE.HLP

```


