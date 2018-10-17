---
title: CloseDatabase 宏操作
TOCTitle: CloseDatabase Macro Action
ms:assetid: c4b4278d-932c-99f6-da2d-8953109b44b3
ms:mtpsurl: https://msdn.microsoft.com/library/Ff823085(v=office.15)
ms:contentKeyID: 48547598
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: d2c60d53b6798d3385bdcfb17669134a04ba6195
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25468847"
---
# <a name="closedatabase-macro-action"></a><span data-ttu-id="9d464-102">CloseDatabase 宏操作</span><span class="sxs-lookup"><span data-stu-id="9d464-102">CloseDatabase Macro Action</span></span>


<span data-ttu-id="9d464-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="9d464-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="9d464-104">可以使用 **CloseDatabase** 操作关闭当前数据库。</span><span class="sxs-lookup"><span data-stu-id="9d464-104">You can use the **CloseDatabase** action to close the current database.</span></span>

## <a name="setting"></a><span data-ttu-id="9d464-105">设置</span><span class="sxs-lookup"><span data-stu-id="9d464-105">Setting</span></span>

<span data-ttu-id="9d464-106">**CloseDatabase** 操作不具有任何参数。</span><span class="sxs-lookup"><span data-stu-id="9d464-106">The **CloseDatabase** action does not have any arguments.</span></span>

## <a name="remarks"></a><span data-ttu-id="9d464-107">说明</span><span class="sxs-lookup"><span data-stu-id="9d464-107">Remarks</span></span>

  - <span data-ttu-id="9d464-108">Access 将不会运行宏中位于 **CloseDatabase** 操作之后的任何操作。</span><span class="sxs-lookup"><span data-stu-id="9d464-108">Access will not run any actions that follow the **CloseDatabase** action in a macro.</span></span>

  - <span data-ttu-id="9d464-109">此操作具有相同的效果单击**文件**选项卡，然后单击**关闭数据库**。</span><span class="sxs-lookup"><span data-stu-id="9d464-109">This action has the same effect as clicking the **File** tab and then clicking **Close Database**.</span></span> <span data-ttu-id="9d464-110">在运行 **CloseDatabase** 操作时，如果有任何未保存的对象处于打开状态，则显示的对话框将与单击 **"关闭数据库"** 时显示的对话框相同。</span><span class="sxs-lookup"><span data-stu-id="9d464-110">If there are any unsaved objects open when you run the **CloseDatabase** action, the dialog boxes that appear are the same as those displayed when you click **Close Database**.</span></span>

  - <span data-ttu-id="9d464-111">要在 Visual Basic for Applications (VBA) 模块中运行 **CloseDatabase** 操作，请使用 **DoCmd** 对象的 **CloseDatabase** 方法。</span><span class="sxs-lookup"><span data-stu-id="9d464-111">To run the **CloseDatabase** action in a Visual Basic for Applications (VBA) module, use the **CloseDatabase** method of the **DoCmd** object.</span></span>
