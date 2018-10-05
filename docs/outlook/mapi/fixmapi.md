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
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25383812"
---
# <a name="fixmapi"></a><span data-ttu-id="7f742-103">FixMAPI</span><span class="sxs-lookup"><span data-stu-id="7f742-103">FixMAPI</span></span>

  
  
<span data-ttu-id="7f742-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="7f742-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="7f742-105">客户端上创建 mapi32.dll 当前副本的备份副本，计算机，并还原 mapi32.dll 与 MAPI 存根库，mapistub.dll。</span><span class="sxs-lookup"><span data-stu-id="7f742-105">Makes a backup copy of the current copy of mapi32.dll on the client computer, and restores mapi32.dll with the MAPI stub library, mapistub.dll.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="7f742-106">快速信息</span><span class="sxs-lookup"><span data-stu-id="7f742-106">Quick info</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="7f742-107">导出：</span><span class="sxs-lookup"><span data-stu-id="7f742-107">Exported by:</span></span>  <br/> |<span data-ttu-id="7f742-108">mapistub.dll</span><span class="sxs-lookup"><span data-stu-id="7f742-108">mapistub.dll</span></span>  <br/> |
|<span data-ttu-id="7f742-109">调用者：</span><span class="sxs-lookup"><span data-stu-id="7f742-109">Called by:</span></span>  <br/> |<span data-ttu-id="7f742-110">客户端</span><span class="sxs-lookup"><span data-stu-id="7f742-110">Client</span></span>  <br/> |
|<span data-ttu-id="7f742-111">实现者：</span><span class="sxs-lookup"><span data-stu-id="7f742-111">Implemented by:</span></span>  <br/> |<span data-ttu-id="7f742-112">Windows</span><span class="sxs-lookup"><span data-stu-id="7f742-112">Windows</span></span>  <br/> |
   
```cpp
DWORD STDAPICALLTYPE FixMAPI(void); 
```

## <a name="return-values"></a><span data-ttu-id="7f742-113">返回值</span><span class="sxs-lookup"><span data-stu-id="7f742-113">Return values</span></span>

<span data-ttu-id="7f742-114">如果函数成功，返回值为非零值。</span><span class="sxs-lookup"><span data-stu-id="7f742-114">If the function succeeds, the return value is a non-zero value.</span></span>
  
<span data-ttu-id="7f742-115">如果函数失败，则返回的值为零。</span><span class="sxs-lookup"><span data-stu-id="7f742-115">If the function fails, the return value is zero.</span></span> <span data-ttu-id="7f742-116">若要获取扩展的错误的信息，请调用的 Microsoft Windows 软件开发工具包 (SDK) 函数，**[时出错](https://msdn.microsoft.com/library/ms679360.aspx)**。</span><span class="sxs-lookup"><span data-stu-id="7f742-116">To get extended error information, call the Microsoft Windows Software Development Kit (SDK) function, **[GetLastError](https://msdn.microsoft.com/library/ms679360.aspx)**.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="7f742-117">说明</span><span class="sxs-lookup"><span data-stu-id="7f742-117">Remarks</span></span>

 <span data-ttu-id="7f742-118">如果该文件标记为只读， **FixMAPI**不替换当前 mapi32.dll 文件。</span><span class="sxs-lookup"><span data-stu-id="7f742-118">**FixMAPI** does not replace the current mapi32.dll file if the file is marked as read-only.</span></span> 
  
 <span data-ttu-id="7f742-119">如果在计算机上安装了 Microsoft Exchange Server **FixMAPI**不替换当前 mapi32.dll。</span><span class="sxs-lookup"><span data-stu-id="7f742-119">**FixMAPI** does not replace the current mapi32.dll if Microsoft Exchange Server is installed on the computer.</span></span> 
  
<span data-ttu-id="7f742-120">当**FixMAPI** mapi32.dll 当前副本的备份副本的计算机上，它会将备份副本分配"mapi32.dll"不同的名称。</span><span class="sxs-lookup"><span data-stu-id="7f742-120">When **FixMAPI** makes a backup copy of the current copy of mapi32.dll on the computer, it assigns the backup copy a name different from "mapi32.dll".</span></span> <span data-ttu-id="7f742-121">然后，它将定向专为备份复制到该程序集的后续呼叫。</span><span class="sxs-lookup"><span data-stu-id="7f742-121">It then directs subsequent calls intended for that assembly to the backup copy.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="7f742-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7f742-122">See also</span></span>



[<span data-ttu-id="7f742-123">KB 256946： 您可以收到程序冲突错误消息，启动 Outlook 2000 时</span><span class="sxs-lookup"><span data-stu-id="7f742-123">KB 256946: You receive a program conflict error message when you start Outlook 2000</span></span>](https://support.microsoft.com/kb/256946)
  
[<span data-ttu-id="7f742-124">KB 228457: Fixmapi.exe 工具的说明包含带有 Internet Explorer 5</span><span class="sxs-lookup"><span data-stu-id="7f742-124">KB 228457: Description of the Fixmapi.exe Tool Included with Internet Explorer 5</span></span>](https://support.microsoft.com/kb/228457)

