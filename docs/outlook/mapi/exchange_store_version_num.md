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
# <a name="exchangestoreversionnum"></a>EXCHANGE_STORE_VERSION_NUM

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
存储 microsoft Office Outlook 配置文件中的帐户连接到的 microsoft Exchange Server 的版本信息。
  
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
  
- 主版本号, 当版本中包含重要的新功能和功能更改时, 通常会增加该版本号。
    
 _wMinorVersion_
  
- 与特定主要版本号相对应且通常在发布包含次要新功能或重大修补程序时递增的次要版本号。
    
 _wBuild_
  
- 与特定主要和次要版本号相对应且在包含新功能或修补程序的内部版本中通常会递增的主要内部版本号。 当 release 是主要的内部代码分支或里程碑 (如候选发布) 时, 此值也会增加。
    
 _wMinorBuild_
  
- 在内部版本中通常递增的次要内部版本号, 其中包含与表示主要代码分支或里程碑的特定主要版本对应的新功能或修补程序。
    
## <a name="see-also"></a>另请参阅



[关于 MAPI 添加件](about-mapi-additions.md)
  
[PidTagProfileServerFullVersion 规范属性](pidtagprofileserverfullversion-canonical-property.md)

