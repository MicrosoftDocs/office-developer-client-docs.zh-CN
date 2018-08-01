---
title: EXCHANGE_STORE_VERSION_NUM
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 88950eda-85ae-ad7a-46c6-0e1933d35e04
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 00d92f8e2ec3af766d5b241d1a911be304b346d6
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774886"
---
# <a name="exchangestoreversionnum"></a>EXCHANGE_STORE_VERSION_NUM

  
  
**适用于**： Outlook 
  
存储在 Microsoft Office Outlook 配置文件中的帐户连接到 Microsoft Exchange Server 版本信息。
  
## <a name="quick-info"></a>快速信息

```cpp
typedef struct { 
    WORD wMajorVersion; 
    WORD wMinorVersion; 
    WORD wBuild; 
    WORD wMinorBuild; 
} EXCHANGE_STORE_VERSION_NUM; 

```

## <a name="members"></a>Members

 _wMajorVersion_
  
- 通常会增加，当发行版中包含大量新功能和更改功能的主要版本号。
    
 _wMinorVersion_
  
- 次要版本数字，对应于特定的主要版本号和发行版中包含次要的新功能或重要修复时通常递增。
    
 _wBuild_
  
- 对应于特定的主要和次要版本号码和，通常会递增在内部版本中包含的新功能或修补程序的主要内部版本号。 主要内部代码分支或里程碑，如候选发布版发行版时，还会递增此值。
    
 _wMinorBuild_
  
- 通常会在内部版本中包含的新功能或修复对应于特定的主要生成表示主要代码分支或里程碑递增的次要版本号。
    
## <a name="see-also"></a>另请参阅



[关于 MAPI 添加件](about-mapi-additions.md)
  
[PidTagProfileServerFullVersion 规范属性](pidtagprofileserverfullversion-canonical-property.md)

