---
title: ConnectPromptEnum （访问桌面数据库参考 （英文）
TOCTitle: ConnectPromptEnum
ms:assetid: 81dff685-b2e4-467e-75cc-b8c5bf80fb75
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249561(v=office.15)
ms:contentKeyID: 48545965
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: e405b1eb3a1326d56a32c432fb212de417cf3469
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25468670"
---
# <a name="connectpromptenum"></a><span data-ttu-id="04efc-102">ConnectPromptEnum</span><span class="sxs-lookup"><span data-stu-id="04efc-102">ConnectPromptEnum</span></span>


<span data-ttu-id="04efc-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="04efc-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="04efc-104">用于指定在打开到数据源的连接时是否应显示对话框，以提示缺少的参数。</span><span class="sxs-lookup"><span data-stu-id="04efc-104">Specifies whether a dialog box should be displayed to prompt for missing parameters when opening a connection to a data source.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="04efc-105">常量</span><span class="sxs-lookup"><span data-stu-id="04efc-105">Constant</span></span></p></th>
<th><p><span data-ttu-id="04efc-106">值</span><span class="sxs-lookup"><span data-stu-id="04efc-106">Value</span></span></p></th>
<th><p><span data-ttu-id="04efc-107">说明</span><span class="sxs-lookup"><span data-stu-id="04efc-107">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="04efc-108"><strong>adPromptAlways</strong></span><span class="sxs-lookup"><span data-stu-id="04efc-108"><strong>adPromptAlways</strong></span></span></p></td>
<td><p><span data-ttu-id="04efc-109">1</span><span class="sxs-lookup"><span data-stu-id="04efc-109">1</span></span></p></td>
<td><p><span data-ttu-id="04efc-110">始终提示。</span><span class="sxs-lookup"><span data-stu-id="04efc-110">Prompts always.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="04efc-111"><strong>adPromptComplete</strong></span><span class="sxs-lookup"><span data-stu-id="04efc-111"><strong>adPromptComplete</strong></span></span></p></td>
<td><p><span data-ttu-id="04efc-112">2</span><span class="sxs-lookup"><span data-stu-id="04efc-112">2</span></span></p></td>
<td><p><span data-ttu-id="04efc-113">当需要更多信息时提示。</span><span class="sxs-lookup"><span data-stu-id="04efc-113">Prompts if more information is required.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="04efc-114"><strong>adPromptCompleteRequired</strong></span><span class="sxs-lookup"><span data-stu-id="04efc-114"><strong>adPromptCompleteRequired</strong></span></span></p></td>
<td><p><span data-ttu-id="04efc-115">3</span><span class="sxs-lookup"><span data-stu-id="04efc-115">3</span></span></p></td>
<td><p><span data-ttu-id="04efc-116">当需要更多信息但不允许可选参数时提示。</span><span class="sxs-lookup"><span data-stu-id="04efc-116">Prompts if more information is required but optional parameters are not allowed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="04efc-117"><strong>adPromptNever</strong></span><span class="sxs-lookup"><span data-stu-id="04efc-117"><strong>adPromptNever</strong></span></span></p></td>
<td><p><span data-ttu-id="04efc-118">4</span><span class="sxs-lookup"><span data-stu-id="04efc-118">4</span></span></p></td>
<td><p><span data-ttu-id="04efc-119">从不提示。</span><span class="sxs-lookup"><span data-stu-id="04efc-119">Never prompts.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="04efc-120">**ADO/WFC 等效值**</span><span class="sxs-lookup"><span data-stu-id="04efc-120">**ADO/WFC Equivalent**</span></span>

<span data-ttu-id="04efc-121">包： **com.ms.wfc.data**</span><span class="sxs-lookup"><span data-stu-id="04efc-121">Package: **com.ms.wfc.data**</span></span>

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="04efc-122">常量</span><span class="sxs-lookup"><span data-stu-id="04efc-122">Constant</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="04efc-123">AdoEnums.ConnectPrompt.ALWAYS</span><span class="sxs-lookup"><span data-stu-id="04efc-123">AdoEnums.ConnectPrompt.ALWAYS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="04efc-124">AdoEnums.ConnectPrompt.COMPLETE</span><span class="sxs-lookup"><span data-stu-id="04efc-124">AdoEnums.ConnectPrompt.COMPLETE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="04efc-125">AdoEnums.ConnectPrompt.COMPLETEREQUIRED</span><span class="sxs-lookup"><span data-stu-id="04efc-125">AdoEnums.ConnectPrompt.COMPLETEREQUIRED</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="04efc-126">AdoEnums.ConnectPrompt.NEVER</span><span class="sxs-lookup"><span data-stu-id="04efc-126">AdoEnums.ConnectPrompt.NEVER</span></span></p></td>
</tr>
</tbody>
</table>

