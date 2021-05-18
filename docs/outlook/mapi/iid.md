---
title: IID
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.IID
api_type:
- COM
ms.assetid: fa5498ab-2f8a-42f8-ba9d-1d555768594f
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 5605de7dbcc18197748713bcf909839690d7259f
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33411594"
---
# <a name="iid"></a><span data-ttu-id="dc4be-103">IID</span><span class="sxs-lookup"><span data-stu-id="dc4be-103">IID</span></span>

  
  
<span data-ttu-id="dc4be-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="dc4be-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="dc4be-105">描述用于描述 MAPI 接口标识符的 [GUID](guid.md) 结构。</span><span class="sxs-lookup"><span data-stu-id="dc4be-105">Describes a [GUID](guid.md) structure used to describe an identifier for a MAPI interface.</span></span> 
  
```cpp
typedef struct _GUID
{
  unsigned long Data1;
  unsigned short Data2;
  unsigned short Data3;
  unsigned char Data4[8];
} GUID;

```

## <a name="members"></a><span data-ttu-id="dc4be-106">Members</span><span class="sxs-lookup"><span data-stu-id="dc4be-106">Members</span></span>

<span data-ttu-id="dc4be-107">请参阅 **GUID** 结构。</span><span class="sxs-lookup"><span data-stu-id="dc4be-107">See the **GUID** structure.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="dc4be-108">备注</span><span class="sxs-lookup"><span data-stu-id="dc4be-108">Remarks</span></span>

<span data-ttu-id="dc4be-109">**IID** 结构用于唯一标识 MAPI 接口并将特定接口与对象关联。</span><span class="sxs-lookup"><span data-stu-id="dc4be-109">An **IID** structure is used to uniquely identify a MAPI interface and to associate a particular interface with an object.</span></span> <span data-ttu-id="dc4be-110">例如，当客户端调用 [IMAPISession：：OpenEntry](imapisession-openentry.md)打开文件夹时，客户端将 _lpInterface_ 参数设置为指向表示 [IMAPIFolder](imapifolderimapicontainer.md)接口的 **IID。**</span><span class="sxs-lookup"><span data-stu-id="dc4be-110">For example, when a client calls [IMAPISession::OpenEntry](imapisession-openentry.md) to open a folder, the client sets the  _lpInterface_ parameter to point to an **IID** representing the [IMAPIFolder](imapifolderimapicontainer.md) interface.</span></span> <span data-ttu-id="dc4be-111">MAPI 定义 **要存储的 IMAPIFolderIID** IID_IMAPIFolder。</span><span class="sxs-lookup"><span data-stu-id="dc4be-111">MAPI defines the **IMAPIFolderIID** to be IID_IMAPIFolder.</span></span> <span data-ttu-id="dc4be-112">**IID** 结构还用于唯一标识 OLE 接口。</span><span class="sxs-lookup"><span data-stu-id="dc4be-112">**IID** structures are also used to uniquely identify OLE interfaces.</span></span> 
  
<span data-ttu-id="dc4be-113">MAPI 接口的所有特定 **IID** 结构在 Mapiguid.h 头文件中定义。</span><span class="sxs-lookup"><span data-stu-id="dc4be-113">All of the specific **IID** structures for the MAPI interfaces are defined in the Mapiguid.h header file.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="dc4be-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dc4be-114">See also</span></span>



[<span data-ttu-id="dc4be-115">GUID</span><span class="sxs-lookup"><span data-stu-id="dc4be-115">GUID</span></span>](guid.md)


[<span data-ttu-id="dc4be-116">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="dc4be-116">MAPI Structures</span></span>](mapi-structures.md)

