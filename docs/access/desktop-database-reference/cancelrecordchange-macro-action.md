---
title: CancelRecordChange 宏操作
TOCTitle: CancelRecordChange Macro Action
ms:assetid: 73031240-1ff6-660b-b25f-11a880df6031
ms:mtpsurl: https://msdn.microsoft.com/library/Ff195846(v=office.15)
ms:contentKeyID: 48545626
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: b1e0cf06436293cbd0c0326a91bd38dcdce5f16a
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25869097"
---
# <a name="cancelrecordchange-macro-action"></a><span data-ttu-id="cc782-102">CancelRecordChange 宏操作</span><span class="sxs-lookup"><span data-stu-id="cc782-102">CancelRecordChange Macro Action</span></span>


<span data-ttu-id="cc782-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="cc782-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="cc782-104">使用 **CancelRecordChange** 操作可在提交更改之前取消在 **[CreateRecord](createrecord-data-block.md)** 或 **[EditRecord](editrecord-data-block.md)** 数据块中对某一记录应用的更改。</span><span class="sxs-lookup"><span data-stu-id="cc782-104">You can use the **CancelRecordChange** action to cancel the changes applied to a record in a **[CreateRecord](createrecord-data-block.md)** or **[EditRecord](editrecord-data-block.md)** data block before the changes are committed.</span></span>


> [!NOTE]
> <span data-ttu-id="cc782-105">[!注释] **CancelRecordChange** 操作仅适用于数据宏。</span><span class="sxs-lookup"><span data-stu-id="cc782-105">The **CancelRecordChange** action is available only in Data Macros.</span></span>



## <a name="remarks"></a><span data-ttu-id="cc782-106">注释</span><span class="sxs-lookup"><span data-stu-id="cc782-106">Remarks</span></span>

<span data-ttu-id="cc782-107">在调用 **CancelRecordChange** 操作时， **CreateRecord** 或 **EditRecord** 数据块将立即退出。</span><span class="sxs-lookup"><span data-stu-id="cc782-107">When you call the **CancelRecordChange** action, the **CreateRecord** or **EditRecord** data block is exited immediately.</span></span>

