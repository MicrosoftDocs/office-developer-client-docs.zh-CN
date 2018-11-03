---
title: 自定义文件 Logs 节
TOCTitle: Customization File Logs section
ms:assetid: de331a97-c9cd-5f02-692b-d7afd9e9342a
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250124(v=office.15)
ms:contentKeyID: 48548178
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: c9a8b9c2255825b135fbc181900a73b3686c64c7
ms.sourcegitcommit: 558d09fad81f8d80b5ad0edd21934fc09c098f2c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2018
ms.locfileid: "25946145"
---
# <a name="customization-file-logs-section"></a><span data-ttu-id="41d2d-102">自定义文件 Logs 节</span><span class="sxs-lookup"><span data-stu-id="41d2d-102">Customization File Logs section</span></span>

<span data-ttu-id="41d2d-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="41d2d-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="41d2d-104">**logs** 节包含日志文件项，该项指定用于在 **DataFactory** 的操作期间记录错误的文件的名称。</span><span class="sxs-lookup"><span data-stu-id="41d2d-104">The **logs** section contains a log file entry, which specifies the name of a file that records errors during the operation of the **DataFactory**.</span></span>

## <a name="syntax"></a><span data-ttu-id="41d2d-105">语法</span><span class="sxs-lookup"><span data-stu-id="41d2d-105">Syntax</span></span>

<span data-ttu-id="41d2d-106">日志文件项的格式为：</span><span class="sxs-lookup"><span data-stu-id="41d2d-106">A log file entry is of the form:</span></span>

`err=FileName`

<br/>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="41d2d-107">部分</span><span class="sxs-lookup"><span data-stu-id="41d2d-107">Part</span></span></p></th>
<th><p><span data-ttu-id="41d2d-108">说明</span><span class="sxs-lookup"><span data-stu-id="41d2d-108">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="41d2d-109"><strong>err</strong></span><span class="sxs-lookup"><span data-stu-id="41d2d-109"><strong>err</strong></span></span></p></td>
<td><p><span data-ttu-id="41d2d-110">字面字符串，用于指示这是日志文件项。</span><span class="sxs-lookup"><span data-stu-id="41d2d-110">A literal string that indicates this is a log file entry.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41d2d-111"><em>FileName</em></span><span class="sxs-lookup"><span data-stu-id="41d2d-111"><em>FileName</em></span></span></p></td>
<td><p><span data-ttu-id="41d2d-p101">完整路径和文件名。典型的文件名是 <strong>c:\msdfmap.log</strong>。</span><span class="sxs-lookup"><span data-stu-id="41d2d-p101">A complete path and file name. The typical file name is <strong>c:\msdfmap.log</strong>.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="41d2d-114">日志文件将包含每个错误的用户名、HRESULT、日期和时间。</span><span class="sxs-lookup"><span data-stu-id="41d2d-114">The log file will contain the user name, HRESULT, date, and time of each error.</span></span>

