---
title: ISocialProviderGetCapabilities
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: f40d5405-12e3-475b-b731-d2223ab70c1d
description: 获取一个字符串，描述提供程序功能。
ms.openlocfilehash: 54e28f22f2dc8fdbe19821d8188087b78c327518
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779221"
---
# <a name="isocialprovidergetcapabilities"></a><span data-ttu-id="2c0e0-103">ISocialProvider::GetCapabilities</span><span class="sxs-lookup"><span data-stu-id="2c0e0-103">ISocialProvider::GetCapabilities</span></span>

<span data-ttu-id="2c0e0-104">获取一个字符串，描述提供程序功能。</span><span class="sxs-lookup"><span data-stu-id="2c0e0-104">Gets a string that describes provider capabilities.</span></span>
  
```cpp
HRESULT _stdcall GetCapabilities([out, retval] BSTR* result);
```

## <a name="parameters"></a><span data-ttu-id="2c0e0-105">参数</span><span class="sxs-lookup"><span data-stu-id="2c0e0-105">Parameters</span></span>

<span data-ttu-id="2c0e0-106">_result_</span><span class="sxs-lookup"><span data-stu-id="2c0e0-106">_result_</span></span>
  
> <span data-ttu-id="2c0e0-107">[输出]一个 XML 字符串值，该值代表 Outlook Social Connector (OSC) 提供程序的功能。</span><span class="sxs-lookup"><span data-stu-id="2c0e0-107">[out] An XML string that represents the capabilities of an Outlook Social Connector (OSC) provider.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="2c0e0-108">说明</span><span class="sxs-lookup"><span data-stu-id="2c0e0-108">Remarks</span></span>

<span data-ttu-id="2c0e0-109">返回的_结果_XML 字符串必须符合**capabilities**元素中，架构定义中的 OSC 提供程序扩展性的 XML 架构定义。</span><span class="sxs-lookup"><span data-stu-id="2c0e0-109">The returned  _result_ XML string must comply with the schema definition for the **capabilities** element, as defined in the XML schema for OSC provider extensibility.</span></span> 
  
<span data-ttu-id="2c0e0-110">提供程序必须返回_结果_字符串要启用对后续调用从 OSC 提供程序才能正常运行。</span><span class="sxs-lookup"><span data-stu-id="2c0e0-110">The provider must return a  _result_ string to enable subsequent calls from the OSC to the provider to operate correctly.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="2c0e0-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2c0e0-111">See also</span></span>

- [<span data-ttu-id="2c0e0-112">ISocialProvider : IUnknown</span><span class="sxs-lookup"><span data-stu-id="2c0e0-112">ISocialProvider : IUnknown</span></span>](isocialprovideriunknown.md)

