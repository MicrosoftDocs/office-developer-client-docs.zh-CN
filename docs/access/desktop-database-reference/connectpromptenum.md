---
title: ConnectPromptEnum (Access desktop database reference)
TOCTitle: ConnectPromptEnum
ms:assetid: 81dff685-b2e4-467e-75cc-b8c5bf80fb75
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249561(v=office.15)
ms:contentKeyID: 48545965
ms.date: 10/18/2018
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 54643a66316d7f534553c20ecc3aafdf755fb857
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32295665"
---
# <a name="connectpromptenum"></a><span data-ttu-id="95f6e-102">ConnectPromptEnum</span><span class="sxs-lookup"><span data-stu-id="95f6e-102">ConnectPromptEnum</span></span>

<span data-ttu-id="95f6e-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="95f6e-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="95f6e-104">用于指定在打开到数据源的连接时是否应显示对话框，以提示缺少的参数。</span><span class="sxs-lookup"><span data-stu-id="95f6e-104">Specifies whether a dialog box should be displayed to prompt for missing parameters when opening a connection to a data source.</span></span>

<br/>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="95f6e-105">常量</span><span class="sxs-lookup"><span data-stu-id="95f6e-105">Constant</span></span></p></th>
<th><p><span data-ttu-id="95f6e-106">值</span><span class="sxs-lookup"><span data-stu-id="95f6e-106">Value</span></span></p></th>
<th><p><span data-ttu-id="95f6e-107">说明</span><span class="sxs-lookup"><span data-stu-id="95f6e-107">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="95f6e-108"><strong>adPromptAlways</strong></span><span class="sxs-lookup"><span data-stu-id="95f6e-108"><strong>adPromptAlways</strong></span></span></p></td>
<td><p><span data-ttu-id="95f6e-109">1</span><span class="sxs-lookup"><span data-stu-id="95f6e-109">1</span></span></p></td>
<td><p><span data-ttu-id="95f6e-110">始终提示。</span><span class="sxs-lookup"><span data-stu-id="95f6e-110">Prompts always.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95f6e-111"><strong>adPromptComplete</strong></span><span class="sxs-lookup"><span data-stu-id="95f6e-111"><strong>adPromptComplete</strong></span></span></p></td>
<td><p><span data-ttu-id="95f6e-112">双面</span><span class="sxs-lookup"><span data-stu-id="95f6e-112">2</span></span></p></td>
<td><p><span data-ttu-id="95f6e-113">当需要更多信息时提示。</span><span class="sxs-lookup"><span data-stu-id="95f6e-113">Prompts if more information is required.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95f6e-114"><strong>adPromptCompleteRequired</strong></span><span class="sxs-lookup"><span data-stu-id="95f6e-114"><strong>adPromptCompleteRequired</strong></span></span></p></td>
<td><p><span data-ttu-id="95f6e-115">第三章</span><span class="sxs-lookup"><span data-stu-id="95f6e-115">3</span></span></p></td>
<td><p><span data-ttu-id="95f6e-116">当需要更多信息但不允许可选参数时提示。</span><span class="sxs-lookup"><span data-stu-id="95f6e-116">Prompts if more information is required but optional parameters are not allowed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95f6e-117"><strong>adPromptNever</strong></span><span class="sxs-lookup"><span data-stu-id="95f6e-117"><strong>adPromptNever</strong></span></span></p></td>
<td><p><span data-ttu-id="95f6e-118">4</span><span class="sxs-lookup"><span data-stu-id="95f6e-118">4</span></span></p></td>
<td><p><span data-ttu-id="95f6e-119">从不提示。</span><span class="sxs-lookup"><span data-stu-id="95f6e-119">Never prompts.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="adowfc-equivalent"></a><span data-ttu-id="95f6e-120">ADO/WFC 等效项</span><span class="sxs-lookup"><span data-stu-id="95f6e-120">ADO/WFC equivalent</span></span>

<span data-ttu-id="95f6e-121">包：**com.ms.wfc.data**</span><span class="sxs-lookup"><span data-stu-id="95f6e-121">Package: **com.ms.wfc.data**</span></span>

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="95f6e-122">常量</span><span class="sxs-lookup"><span data-stu-id="95f6e-122">Constant</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="95f6e-123">AdoEnums ConnectPrompt。始终</span><span class="sxs-lookup"><span data-stu-id="95f6e-123">AdoEnums.ConnectPrompt.ALWAYS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95f6e-124">AdoEnums 的完整 ConnectPrompt</span><span class="sxs-lookup"><span data-stu-id="95f6e-124">AdoEnums.ConnectPrompt.COMPLETE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95f6e-125">AdoEnums ConnectPrompt</span><span class="sxs-lookup"><span data-stu-id="95f6e-125">AdoEnums.ConnectPrompt.COMPLETEREQUIRED</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95f6e-126">AdoEnums ConnectPrompt。从不</span><span class="sxs-lookup"><span data-stu-id="95f6e-126">AdoEnums.ConnectPrompt.NEVER</span></span></p></td>
</tr>
</tbody>
</table>

