---
title: 'DeleteRecord Access 自定义 Web (的 DeleteRecord 数据宏) '
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
localization_priority: Normal
ms.assetid: f6b68a9a-e04a-476e-a407-b1779fea1953
description: 可以使用 DeleteRecord 操作删除记录。
ms.openlocfilehash: 0e8a658b944e894e4d4014fb3d3d9a583efbee8d
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33423151"
---
# <a name="deleterecord-data-macro-action-access-custom-web-app"></a><span data-ttu-id="1f12f-103">DeleteRecord Access 自定义 Web (的 DeleteRecord 数据宏) </span><span class="sxs-lookup"><span data-stu-id="1f12f-103">DeleteRecord Data Macro action (Access custom web app)</span></span>

<span data-ttu-id="1f12f-104">可以使用 **DeleteRecord** 操作删除记录。</span><span class="sxs-lookup"><span data-stu-id="1f12f-104">You can use the **DeleteRecord** action to delete a record.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="1f12f-p101">Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。</span><span class="sxs-lookup"><span data-stu-id="1f12f-p101">Microsoft no longer recommends creating and using Access web apps in SharePoint. As an alternative, consider using [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/) to build no-code business solutions for the web and mobile devices.</span></span> 
  
## <a name="setting"></a><span data-ttu-id="1f12f-107">设置</span><span class="sxs-lookup"><span data-stu-id="1f12f-107">Setting</span></span>

<span data-ttu-id="1f12f-108">**DeleteRecord** 操作具有下列参数。</span><span class="sxs-lookup"><span data-stu-id="1f12f-108">The **DeleteRecord** action has the following arguments.</span></span> 
  
|<span data-ttu-id="1f12f-109">**参数**</span><span class="sxs-lookup"><span data-stu-id="1f12f-109">**Argument**</span></span>|<span data-ttu-id="1f12f-110">**说明**</span><span class="sxs-lookup"><span data-stu-id="1f12f-110">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1f12f-111">**Record Alias**</span><span class="sxs-lookup"><span data-stu-id="1f12f-111">**Record Alias**</span></span> <br/> |<span data-ttu-id="1f12f-112">一个用于标识要删除的记录的字符串。</span><span class="sxs-lookup"><span data-stu-id="1f12f-112">A string that identifies the record to delete.</span></span> <span data-ttu-id="1f12f-113">如果  *未指定 Alias*  参数，则删除当前记录。</span><span class="sxs-lookup"><span data-stu-id="1f12f-113">If the  *Alias*  argument is not specified, then the current record is deleted.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="1f12f-114">备注</span><span class="sxs-lookup"><span data-stu-id="1f12f-114">Remarks</span></span>

<span data-ttu-id="1f12f-115">您可以使用 **LastCreateRecordIdentity** 本地变量来处理在 **CreateRecord** 数据块中创建的最后一条记录。</span><span class="sxs-lookup"><span data-stu-id="1f12f-115">You can use the **LastCreateRecordIdentity** local variable to work with last record created in a **CreateRecord** data block.</span></span> <span data-ttu-id="1f12f-116">例如，使用以下语法引用最近创建的记录：</span><span class="sxs-lookup"><span data-stu-id="1f12f-116">For example, use the following syntax to refer to the most recently created record:</span></span> 
  
`[LastCreateRecordIdentity]`


