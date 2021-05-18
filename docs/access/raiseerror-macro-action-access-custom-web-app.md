---
title: 'RaiseError 宏操作 (Access 自定义 Web 应用) '
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 5e29bf64-300a-4094-82ff-664e79782d86
description: RaiseError 操作显示一个弹出窗口，其中包含指定的错误消息。
ms.openlocfilehash: 49e544d2234759709c19052b5540d42e88070849
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33408241"
---
# <a name="raiseerror-macro-action-access-custom-web-app"></a><span data-ttu-id="667ed-103">RaiseError 宏操作 (Access 自定义 Web 应用) </span><span class="sxs-lookup"><span data-stu-id="667ed-103">RaiseError Macro Action (Access custom web app)</span></span>

<span data-ttu-id="667ed-104">**RaiseError** 操作显示一个弹出窗口，其中包含指定的错误消息。</span><span class="sxs-lookup"><span data-stu-id="667ed-104">The **RaiseError** action displays a popup window that contains a specified error message.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="667ed-p101">Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。</span><span class="sxs-lookup"><span data-stu-id="667ed-p101">Microsoft no longer recommends creating and using Access web apps in SharePoint. As an alternative, consider using [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/) to build no-code business solutions for the web and mobile devices.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="667ed-107">**RaiseError** 操作仅适用于数据宏。</span><span class="sxs-lookup"><span data-stu-id="667ed-107">The **RaiseError** action is available only in Data Macros.</span></span> 
  
## <a name="setting"></a><span data-ttu-id="667ed-108">设置</span><span class="sxs-lookup"><span data-stu-id="667ed-108">Setting</span></span>

<span data-ttu-id="667ed-109">**RaiseError** 操作具有以下参数。</span><span class="sxs-lookup"><span data-stu-id="667ed-109">The **RaiseError** action has the following argument.</span></span> 
  
|<span data-ttu-id="667ed-110">**参数**</span><span class="sxs-lookup"><span data-stu-id="667ed-110">**Argument**</span></span>|<span data-ttu-id="667ed-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="667ed-111">**Description**</span></span>|
|:-----|:-----|
| <span data-ttu-id="667ed-112">_Error Description_</span><span class="sxs-lookup"><span data-stu-id="667ed-112">_Error Description_</span></span> <br/> |<span data-ttu-id="667ed-113">一个描述错误的字符串表达式。</span><span class="sxs-lookup"><span data-stu-id="667ed-113">A string expression that describes the error.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="667ed-114">备注</span><span class="sxs-lookup"><span data-stu-id="667ed-114">Remarks</span></span>

<span data-ttu-id="667ed-115">调用 **RaiseError** 操作时，将回滚当前事务中所有操作。</span><span class="sxs-lookup"><span data-stu-id="667ed-115">When the **RaiseError** action is called, all of the operations in the current transaction are rolled back.</span></span> 
  

