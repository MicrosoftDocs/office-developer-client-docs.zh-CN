---
title: DeleteRecord 数据宏操作 （访问自定义 web 应用程序）
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
localization_priority: Normal
ms.assetid: f6b68a9a-e04a-476e-a407-b1779fea1953
description: 可以使用 DeleteRecord 操作删除记录。
ms.openlocfilehash: 64742d73ec57b94474c8e27822fd3946c7673336
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773404"
---
# <a name="deleterecord-data-macro-action-access-custom-web-app"></a><span data-ttu-id="a9437-103">DeleteRecord 数据宏操作 （访问自定义 web 应用程序）</span><span class="sxs-lookup"><span data-stu-id="a9437-103">DeleteRecord Data Macro action (Access custom web app)</span></span>

<span data-ttu-id="a9437-104">可以使用 **DeleteRecord** 操作删除记录。</span><span class="sxs-lookup"><span data-stu-id="a9437-104">You can use the **DeleteRecord** action to delete a record.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="a9437-p101">Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。</span><span class="sxs-lookup"><span data-stu-id="a9437-p101">Microsoft no longer recommends creating and using Access web apps in SharePoint. As an alternative, consider using [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/) to build no-code business solutions for the web and mobile devices.</span></span> 
  
## <a name="setting"></a><span data-ttu-id="a9437-107">设置</span><span class="sxs-lookup"><span data-stu-id="a9437-107">Setting</span></span>

<span data-ttu-id="a9437-108">**DeleteRecord**操作具有下列参数。</span><span class="sxs-lookup"><span data-stu-id="a9437-108">The **DeleteRecord** action has the following arguments.</span></span> 
  
|<span data-ttu-id="a9437-109">**参数**</span><span class="sxs-lookup"><span data-stu-id="a9437-109">**Argument**</span></span>|<span data-ttu-id="a9437-110">**说明**</span><span class="sxs-lookup"><span data-stu-id="a9437-110">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a9437-111">**Record Alias**</span><span class="sxs-lookup"><span data-stu-id="a9437-111">**Record Alias**</span></span> <br/> |<span data-ttu-id="a9437-112">一个字符串，标识要删除的记录。</span><span class="sxs-lookup"><span data-stu-id="a9437-112">A string that identifies the record to delete.</span></span> <span data-ttu-id="a9437-113">如果未指定*别名*参数，将删除当前记录。</span><span class="sxs-lookup"><span data-stu-id="a9437-113">If the  *Alias*  argument is not specified, then the current record is deleted.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="a9437-114">注释</span><span class="sxs-lookup"><span data-stu-id="a9437-114">Remarks</span></span>

<span data-ttu-id="a9437-115">您可以使用 **LastCreateRecordIdentity** 本地变量来处理在 **CreateRecord** 数据块中创建的最后一条记录。</span><span class="sxs-lookup"><span data-stu-id="a9437-115">You can use the **LastCreateRecordIdentity** local variable to work with last record created in a **CreateRecord** data block.</span></span> <span data-ttu-id="a9437-116">例如，使用以下语法引用最近创建的记录：</span><span class="sxs-lookup"><span data-stu-id="a9437-116">For example, use the following syntax to refer to the most recently created record:</span></span> 
  
`[LastCreateRecordIdentity]`


