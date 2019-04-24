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
# <a name="fixmapi"></a><span data-ttu-id="88941-103">FixMAPI</span><span class="sxs-lookup"><span data-stu-id="88941-103">FixMAPI</span></span>

  
  
<span data-ttu-id="88941-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="88941-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="88941-105">在客户端计算机上创建 mapi32 的当前副本的备份副本, 并使用 MAPI 存根库 (mapistub) 还原 mapi32。</span><span class="sxs-lookup"><span data-stu-id="88941-105">Makes a backup copy of the current copy of mapi32.dll on the client computer, and restores mapi32.dll with the MAPI stub library, mapistub.dll.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="88941-106">快速信息</span><span class="sxs-lookup"><span data-stu-id="88941-106">Quick info</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="88941-107">导出者:</span><span class="sxs-lookup"><span data-stu-id="88941-107">Exported by:</span></span>  <br/> |<span data-ttu-id="88941-108">mapistub</span><span class="sxs-lookup"><span data-stu-id="88941-108">mapistub.dll</span></span>  <br/> |
|<span data-ttu-id="88941-109">调用者：</span><span class="sxs-lookup"><span data-stu-id="88941-109">Called by:</span></span>  <br/> |<span data-ttu-id="88941-110">客户端</span><span class="sxs-lookup"><span data-stu-id="88941-110">Client</span></span>  <br/> |
|<span data-ttu-id="88941-111">实现者：</span><span class="sxs-lookup"><span data-stu-id="88941-111">Implemented by:</span></span>  <br/> |<span data-ttu-id="88941-112">Windows</span><span class="sxs-lookup"><span data-stu-id="88941-112">Windows</span></span>  <br/> |
   
```cpp
DWORD STDAPICALLTYPE FixMAPI(void); 
```

## <a name="return-values"></a><span data-ttu-id="88941-113">返回值</span><span class="sxs-lookup"><span data-stu-id="88941-113">Return values</span></span>

<span data-ttu-id="88941-114">如果函数成功, 则返回值为非零值。</span><span class="sxs-lookup"><span data-stu-id="88941-114">If the function succeeds, the return value is a non-zero value.</span></span>
  
<span data-ttu-id="88941-115">如果函数失败, 则返回的值为零。</span><span class="sxs-lookup"><span data-stu-id="88941-115">If the function fails, the return value is zero.</span></span> <span data-ttu-id="88941-116">若要获取扩展的错误消息, 请调用 Microsoft Windows 软件开发工具包 (SDK) 函数 ( **[GetLastError](https://msdn.microsoft.com/library/ms679360.aspx)**)。</span><span class="sxs-lookup"><span data-stu-id="88941-116">To get extended error information, call the Microsoft Windows Software Development Kit (SDK) function, **[GetLastError](https://msdn.microsoft.com/library/ms679360.aspx)**.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="88941-117">注解</span><span class="sxs-lookup"><span data-stu-id="88941-117">Remarks</span></span>

 <span data-ttu-id="88941-118">如果文件被标记为只读, 则**FixMAPI**不会替换当前的 mapi32 文件。</span><span class="sxs-lookup"><span data-stu-id="88941-118">**FixMAPI** does not replace the current mapi32.dll file if the file is marked as read-only.</span></span> 
  
 <span data-ttu-id="88941-119">如果计算机上安装了 Microsoft Exchange Server, **FixMAPI**不会替换当前的 mapi32。</span><span class="sxs-lookup"><span data-stu-id="88941-119">**FixMAPI** does not replace the current mapi32.dll if Microsoft Exchange Server is installed on the computer.</span></span> 
  
<span data-ttu-id="88941-120">当**FixMAPI**在计算机上制作 mapi32 的当前副本的备份副本时, 它会为备份副本分配一个不同于 "mapi32" 的名称。</span><span class="sxs-lookup"><span data-stu-id="88941-120">When **FixMAPI** makes a backup copy of the current copy of mapi32.dll on the computer, it assigns the backup copy a name different from "mapi32.dll".</span></span> <span data-ttu-id="88941-121">然后, 它将为该程序集预定的后续调用定向到备份副本。</span><span class="sxs-lookup"><span data-stu-id="88941-121">It then directs subsequent calls intended for that assembly to the backup copy.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="88941-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="88941-122">See also</span></span>



[<span data-ttu-id="88941-123">KB 256946: 启动 Outlook 2000 时收到程序冲突错误消息</span><span class="sxs-lookup"><span data-stu-id="88941-123">KB 256946: You receive a program conflict error message when you start Outlook 2000</span></span>](https://support.microsoft.com/kb/256946)
  
[<span data-ttu-id="88941-124">KB 228457: Internet Explorer 5 附带的 Fixmapi 工具的说明</span><span class="sxs-lookup"><span data-stu-id="88941-124">KB 228457: Description of the Fixmapi.exe Tool Included with Internet Explorer 5</span></span>](https://support.microsoft.com/kb/228457)

