---
title: IMSCapabilitiesGetCapabilities
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMSCapabilities.GetCapabilities
api_type:
- COM
ms.assetid: c77a8ef1-0730-d458-b35f-451d3f450fac
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 0211a326e94c5847c040040e0e0e4e9ddd1d760d
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22583272"
---
# <a name="imscapabilitiesgetcapabilities"></a>IMSCapabilities::GetCapabilities

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
获取有关存储可支持信息基于指定的选择器。
  
```cpp
ULONG GetCapabilities( 
MSCAP_SELECTOR mscapSelector 
);
```

## <a name="parameters"></a>参数

 *mscapSelector* 
  
> [in]指示要返回哪些功能的选择器。
    
## <a name="return-value"></a>返回值

MSCAP_SECURE_FOLDER_HOMEPAGES
  
> 支持的非默认存储区中的文件夹主页。 这可以返回如果**MSCAP_SEL_FOLDER** *mscapSelector*中指定。 
    
MSCAP_RES_ANNOTATION
  
> 如果限制包含任何无效的参数，例如无效的属性，存储将忽略参数无效，处理仅的有效参数。 这可以返回如果**MSCAP_SEL_RESTRICTION** *mscapSelector*中指定。 
    
NULL
  
> 存储不支持基于给定的选择器任何功能。
    

