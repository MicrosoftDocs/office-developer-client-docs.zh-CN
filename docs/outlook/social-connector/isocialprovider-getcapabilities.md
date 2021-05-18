---
title: ISocialProviderGetCapabilities
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: f40d5405-12e3-475b-b731-d2223ab70c1d
description: 获取一个描述提供程序功能的字符串。
ms.openlocfilehash: cf3d1418ac0ecbfc3f67bb550a24ec71781f2637
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33408101"
---
# <a name="isocialprovidergetcapabilities"></a><span data-ttu-id="7bd14-103">ISocialProvider::GetCapabilities</span><span class="sxs-lookup"><span data-stu-id="7bd14-103">ISocialProvider::GetCapabilities</span></span>

<span data-ttu-id="7bd14-104">获取一个描述提供程序功能的字符串。</span><span class="sxs-lookup"><span data-stu-id="7bd14-104">Gets a string that describes provider capabilities.</span></span>
  
```cpp
HRESULT _stdcall GetCapabilities([out, retval] BSTR* result);
```

## <a name="parameters"></a><span data-ttu-id="7bd14-105">参数</span><span class="sxs-lookup"><span data-stu-id="7bd14-105">Parameters</span></span>

<span data-ttu-id="7bd14-106">_result_</span><span class="sxs-lookup"><span data-stu-id="7bd14-106">_result_</span></span>
  
> <span data-ttu-id="7bd14-107">[out]一个 XML 字符串，表示 OSC Outlook (连接器) 的功能。</span><span class="sxs-lookup"><span data-stu-id="7bd14-107">[out] An XML string that represents the capabilities of an Outlook Social Connector (OSC) provider.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="7bd14-108">备注</span><span class="sxs-lookup"><span data-stu-id="7bd14-108">Remarks</span></span>

<span data-ttu-id="7bd14-109">返回  _的结果_ XML 字符串必须符合 **capabilities** 元素的架构定义，如 OSC 提供程序扩展性 XML 架构中的定义。</span><span class="sxs-lookup"><span data-stu-id="7bd14-109">The returned  _result_ XML string must comply with the schema definition for the **capabilities** element, as defined in the XML schema for OSC provider extensibility.</span></span> 
  
<span data-ttu-id="7bd14-110">提供程序必须  _返回结果字符串_ ，以使 OSC 对提供程序的后续调用能够正常运行。</span><span class="sxs-lookup"><span data-stu-id="7bd14-110">The provider must return a  _result_ string to enable subsequent calls from the OSC to the provider to operate correctly.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="7bd14-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7bd14-111">See also</span></span>

- [<span data-ttu-id="7bd14-112">ISocialProvider : IUnknown</span><span class="sxs-lookup"><span data-stu-id="7bd14-112">ISocialProvider : IUnknown</span></span>](isocialprovideriunknown.md)

