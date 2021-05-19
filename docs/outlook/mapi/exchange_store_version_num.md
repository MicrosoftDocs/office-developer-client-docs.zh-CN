---
title: EXCHANGE_STORE_VERSION_NUM
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 88950eda-85ae-ad7a-46c6-0e1933d35e04
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: bf60b12a6e4575d3504a112aa2b54fb8c4ae23c7
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33433722"
---
# <a name="exchange_store_version_num"></a>EXCHANGE_STORE_VERSION_NUM

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
存储帐户连接到Microsoft Exchange Server配置文件中的Microsoft Office Outlook版本信息。
  
## <a name="quick-info"></a>快速信息

```cpp
typedef struct { 
    WORD wMajorVersion; 
    WORD wMinorVersion; 
    WORD wBuild; 
    WORD wMinorBuild; 
} EXCHANGE_STORE_VERSION_NUM; 

```

## <a name="members"></a>成员

 _wMajorVersion_
  
- 当版本包含重大新功能和功能更改时通常递增的主要版本号。
    
 _wMinorVersion_
  
- 与特定主要版本号对应的次要版本号，当版本包含次要新功能或重要修补程序时通常递增。
    
 _wBuild_
  
- 与特定主要版本号和次要版本号相对应的主要版本号，通常在包含新功能或修补程序的内部版本中递增。 当版本是主要的内部代码分支或里程碑（如候选发布）时，此值也会递增。
    
 _wMinorBuild_
  
- 内部版本中通常递增的次要内部版本编号，其中包含与表示主要代码分支或里程碑的特定主要内部版本对应的新功能或修补程序。
    
## <a name="see-also"></a>另请参阅



[关于 MAPI 添加件](about-mapi-additions.md)
  
[PidTagProfileServerFullVersion 规范属性](pidtagprofileserverfullversion-canonical-property.md)

