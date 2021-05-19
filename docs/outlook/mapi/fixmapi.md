---
title: FixMAPI
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 32676003-ba32-886f-1185-4760cb0e30e3
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 2aeca1a65a859ac9502995a463bc4869609bcd15
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32334959"
---
# <a name="fixmapi"></a><span data-ttu-id="ada90-103">FixMAPI</span><span class="sxs-lookup"><span data-stu-id="ada90-103">FixMAPI</span></span>

  
  
<span data-ttu-id="ada90-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="ada90-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="ada90-105">在客户端计算机上创建当前 mapi32.dll 副本的备份副本，并还原mapi32.dll MAPI 存根库mapistub.dll。</span><span class="sxs-lookup"><span data-stu-id="ada90-105">Makes a backup copy of the current copy of mapi32.dll on the client computer, and restores mapi32.dll with the MAPI stub library, mapistub.dll.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="ada90-106">快速信息</span><span class="sxs-lookup"><span data-stu-id="ada90-106">Quick info</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="ada90-107">导出者：</span><span class="sxs-lookup"><span data-stu-id="ada90-107">Exported by:</span></span>  <br/> |<span data-ttu-id="ada90-108">mapistub.dll</span><span class="sxs-lookup"><span data-stu-id="ada90-108">mapistub.dll</span></span>  <br/> |
|<span data-ttu-id="ada90-109">调用者：</span><span class="sxs-lookup"><span data-stu-id="ada90-109">Called by:</span></span>  <br/> |<span data-ttu-id="ada90-110">客户端</span><span class="sxs-lookup"><span data-stu-id="ada90-110">Client</span></span>  <br/> |
|<span data-ttu-id="ada90-111">实现者：</span><span class="sxs-lookup"><span data-stu-id="ada90-111">Implemented by:</span></span>  <br/> |<span data-ttu-id="ada90-112">Windows</span><span class="sxs-lookup"><span data-stu-id="ada90-112">Windows</span></span>  <br/> |
   
```cpp
DWORD STDAPICALLTYPE FixMAPI(void); 
```

## <a name="return-values"></a><span data-ttu-id="ada90-113">返回值</span><span class="sxs-lookup"><span data-stu-id="ada90-113">Return values</span></span>

<span data-ttu-id="ada90-114">如果函数成功，则返回值为非零值。</span><span class="sxs-lookup"><span data-stu-id="ada90-114">If the function succeeds, the return value is a non-zero value.</span></span>
  
<span data-ttu-id="ada90-115">如果函数失败，则返回值为 0。</span><span class="sxs-lookup"><span data-stu-id="ada90-115">If the function fails, the return value is zero.</span></span> <span data-ttu-id="ada90-116">若要获取扩展的错误信息，请调用 Microsoft Windows Software Development Kit (SDK) 函数 **[GetLastError](https://msdn.microsoft.com/library/ms679360.aspx)**。</span><span class="sxs-lookup"><span data-stu-id="ada90-116">To get extended error information, call the Microsoft Windows Software Development Kit (SDK) function, **[GetLastError](https://msdn.microsoft.com/library/ms679360.aspx)**.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="ada90-117">备注</span><span class="sxs-lookup"><span data-stu-id="ada90-117">Remarks</span></span>

 <span data-ttu-id="ada90-118">**FixMAPI** 不会替换当前mapi32.dll文件，如果该文件标记为只读。</span><span class="sxs-lookup"><span data-stu-id="ada90-118">**FixMAPI** does not replace the current mapi32.dll file if the file is marked as read-only.</span></span> 
  
 <span data-ttu-id="ada90-119">**FixMAPI** 不会替换当前mapi32.dll如果Microsoft Exchange Server安装当前服务器。</span><span class="sxs-lookup"><span data-stu-id="ada90-119">**FixMAPI** does not replace the current mapi32.dll if Microsoft Exchange Server is installed on the computer.</span></span> 
  
<span data-ttu-id="ada90-120">当 **FixMAPI** 在计算机上创建当前 mapi32.dll 副本的备份副本时，它会为备份副本分配一个不同于"mapi32.dll"的名称。</span><span class="sxs-lookup"><span data-stu-id="ada90-120">When **FixMAPI** makes a backup copy of the current copy of mapi32.dll on the computer, it assigns the backup copy a name different from "mapi32.dll".</span></span> <span data-ttu-id="ada90-121">然后，它将针对该程序集的后续调用引导到备份副本。</span><span class="sxs-lookup"><span data-stu-id="ada90-121">It then directs subsequent calls intended for that assembly to the backup copy.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="ada90-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ada90-122">See also</span></span>



[<span data-ttu-id="ada90-123">KB 256946：在启动 2000 时收到Outlook错误消息</span><span class="sxs-lookup"><span data-stu-id="ada90-123">KB 256946: You receive a program conflict error message when you start Outlook 2000</span></span>](https://support.microsoft.com/kb/256946)
  
[<span data-ttu-id="ada90-124">KB 228457：Fixmapi.exe工具的说明 5 Internet Explorer 5</span><span class="sxs-lookup"><span data-stu-id="ada90-124">KB 228457: Description of the Fixmapi.exe Tool Included with Internet Explorer 5</span></span>](https://support.microsoft.com/kb/228457)

