---
title: RaiseError 宏操作 （访问自定义 web 应用程序）
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 5e29bf64-300a-4094-82ff-664e79782d86
description: RaiseError 操作显示包含指定的错误消息的弹出窗口。
ms.openlocfilehash: 1176804106c5cfd9d4bd30f79f47975593089dbc
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773590"
---
# <a name="raiseerror-macro-action-access-custom-web-app"></a><span data-ttu-id="e4256-103">RaiseError 宏操作 （访问自定义 web 应用程序）</span><span class="sxs-lookup"><span data-stu-id="e4256-103">RaiseError Macro Action (Access custom web app)</span></span>

<span data-ttu-id="e4256-104">**RaiseError**操作显示包含指定的错误消息的弹出窗口。</span><span class="sxs-lookup"><span data-stu-id="e4256-104">The **RaiseError** action displays a popup window that contains a specified error message.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="e4256-p101">Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。</span><span class="sxs-lookup"><span data-stu-id="e4256-p101">Microsoft no longer recommends creating and using Access web apps in SharePoint. As an alternative, consider using [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/) to build no-code business solutions for the web and mobile devices.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="e4256-107">**RaiseError** 操作仅适用于数据宏。</span><span class="sxs-lookup"><span data-stu-id="e4256-107">The **RaiseError** action is available only in Data Macros.</span></span> 
  
## <a name="setting"></a><span data-ttu-id="e4256-108">设置</span><span class="sxs-lookup"><span data-stu-id="e4256-108">Setting</span></span>

<span data-ttu-id="e4256-109">**RaiseError**操作具有以下参数。</span><span class="sxs-lookup"><span data-stu-id="e4256-109">The **RaiseError** action has the following argument.</span></span> 
  
|<span data-ttu-id="e4256-110">**参数**</span><span class="sxs-lookup"><span data-stu-id="e4256-110">**Argument**</span></span>|<span data-ttu-id="e4256-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="e4256-111">**Description**</span></span>|
|:-----|:-----|
| <span data-ttu-id="e4256-112">_错误说明_</span><span class="sxs-lookup"><span data-stu-id="e4256-112">_Error Description_</span></span> <br/> |<span data-ttu-id="e4256-113">一个描述错误的字符串表达式。</span><span class="sxs-lookup"><span data-stu-id="e4256-113">A string expression that describes the error.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="e4256-114">注释</span><span class="sxs-lookup"><span data-stu-id="e4256-114">Remarks</span></span>

<span data-ttu-id="e4256-115">当调用**RaiseError**操作时，所有当前事务中的操作将被回滚。</span><span class="sxs-lookup"><span data-stu-id="e4256-115">When the **RaiseError** action is called, all of the operations in the current transaction are rolled back.</span></span> 
  

