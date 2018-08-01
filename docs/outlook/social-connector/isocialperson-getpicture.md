---
title: ISocialPersonGetPicture
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 02fcaf25-42b5-4584-95c6-d44a3d035128
description: 获取包含此人的图片资源的字节数组。
ms.openlocfilehash: dcb0da5bc36c2166d569c770d1f182cd21339435
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779210"
---
# <a name="isocialpersongetpicture"></a><span data-ttu-id="86db2-103">ISocialPerson::GetPicture</span><span class="sxs-lookup"><span data-stu-id="86db2-103">ISocialPerson::GetPicture</span></span>

<span data-ttu-id="86db2-104">获取包含此人的图片资源的字节数组。</span><span class="sxs-lookup"><span data-stu-id="86db2-104">Gets an array of bytes that contains the picture resource for the person.</span></span> 
  
```cpp
HRESULT _stdcall GetPicture([out, retval] SAFEARRAY(unsigned char)* picture);
```

## <a name="parameters"></a><span data-ttu-id="86db2-105">参数</span><span class="sxs-lookup"><span data-stu-id="86db2-105">Parameters</span></span>

<span data-ttu-id="86db2-106">_图片_</span><span class="sxs-lookup"><span data-stu-id="86db2-106">_picture_</span></span>
  
> <span data-ttu-id="86db2-107">[输出]一个指向指定一个表示图片资源的人员的字节数组的结构。</span><span class="sxs-lookup"><span data-stu-id="86db2-107">[out] A pointer to a structure that specifies an array of bytes that represent the picture resource for a person.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="86db2-108">说明</span><span class="sxs-lookup"><span data-stu-id="86db2-108">Remarks</span></span>

<span data-ttu-id="86db2-109">支持资源是.bmp、.jpeg 或.png 格式中的图片。</span><span class="sxs-lookup"><span data-stu-id="86db2-109">Supported picture resources are in .bmp, .jpeg, or .png format.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="86db2-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="86db2-110">See also</span></span>

- [<span data-ttu-id="86db2-111">ISocialPerson : IUnknown</span><span class="sxs-lookup"><span data-stu-id="86db2-111">ISocialPerson : IUnknown</span></span>](isocialpersoniunknown.md)

