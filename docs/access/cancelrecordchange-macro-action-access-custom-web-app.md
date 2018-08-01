---
title: CancelRecordChange 宏操作 （访问自定义 web 应用程序）
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
localization_priority: Normal
ms.assetid: cbdbee8c-70d6-45df-a56b-5f7c6e5bdc6d
description: 使用 CancelRecordChange 操作可在提交更改之前取消在 CreateRecord 或 EditRecord 数据块中对某一记录应用的更改。
ms.openlocfilehash: 5f5d131ce8662dbd290a30ea08594cb413791d5c
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773456"
---
# <a name="cancelrecordchange-macro-action-access-custom-web-app"></a><span data-ttu-id="3859e-103">CancelRecordChange 宏操作 （访问自定义 web 应用程序）</span><span class="sxs-lookup"><span data-stu-id="3859e-103">CancelRecordChange Macro Action (Access custom web app)</span></span>

<span data-ttu-id="3859e-104">使用 **CancelRecordChange** 操作可在提交更改之前取消在 **[CreateRecord](createrecord-data-block-access-custom-web-app.md)** 或 **[EditRecord](editrecord-data-block-access-custom-web-app.md)** 数据块中对某一记录应用的更改。</span><span class="sxs-lookup"><span data-stu-id="3859e-104">You can use the **CancelRecordChange** action to cancel the changes applied to a record in a **[CreateRecord](createrecord-data-block-access-custom-web-app.md)** or **[EditRecord](editrecord-data-block-access-custom-web-app.md)** data block before the changes are committed.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="3859e-p101">Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。</span><span class="sxs-lookup"><span data-stu-id="3859e-p101">Microsoft no longer recommends creating and using Access web apps in SharePoint. As an alternative, consider using [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/) to build no-code business solutions for the web and mobile devices.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="3859e-107">[!注释] **CancelRecordChange** 操作仅适用于数据宏。</span><span class="sxs-lookup"><span data-stu-id="3859e-107">The **CancelRecordChange** action is available only in Data Macros.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="3859e-108">注释</span><span class="sxs-lookup"><span data-stu-id="3859e-108">Remarks</span></span>

<span data-ttu-id="3859e-109">在调用 **CancelRecordChange** 操作时， **CreateRecord** 或 **EditRecord** 数据块将立即退出。</span><span class="sxs-lookup"><span data-stu-id="3859e-109">When you call the **CancelRecordChange** action, the **CreateRecord** or **EditRecord** data block is exited immediately.</span></span> 
  

