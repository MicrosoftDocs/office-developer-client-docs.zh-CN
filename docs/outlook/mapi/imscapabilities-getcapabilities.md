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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: b76c55fd9ddc3aa7698f75aa6ce965544b2c9aae
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33409256"
---
# <a name="imscapabilitiesgetcapabilities"></a>IMSCapabilities::GetCapabilities

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
根据指定的选择器，获取应用商店可以支持哪些内容的信息。
  
```cpp
ULONG GetCapabilities( 
MSCAP_SELECTOR mscapSelector 
);
```

## <a name="parameters"></a>参数

 *mscapSelector* 
  
> [in]指示要返回的功能的选择器。
    
## <a name="return-value"></a>返回值

MSCAP_SECURE_FOLDER_HOMEPAGES
  
> 支持非默认应用商店中的文件夹主页。 如果在 *mscapSelector* **中MSCAP_SEL_FOLDER，** 则可能会返回此参数。 
    
MSCAP_RES_ANNOTATION
  
> 如果限制包含任何无效参数（如无效属性），则存储将忽略无效参数并仅处理有效参数。 如果在 *mscapSelector* **中MSCAP_SEL_RESTRICTION，** 则可能会返回此参数。 
    
NULL
  
> 存储不支持基于给定选择器的任何功能。
    

