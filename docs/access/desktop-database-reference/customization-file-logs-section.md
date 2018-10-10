---
title: 自定义文件 Logs 节
TOCTitle: Customization File Logs Section
ms:assetid: de331a97-c9cd-5f02-692b-d7afd9e9342a
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250124(v=office.15)
ms:contentKeyID: 48548178
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 479bac0c61718f12af8fcb1b176b91d3fc57841b
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25468308"
---
# <a name="customization-file-logs-section"></a><span data-ttu-id="8e0ca-102">自定义文件 Logs 节</span><span class="sxs-lookup"><span data-stu-id="8e0ca-102">Customization File Logs Section</span></span>

<span data-ttu-id="8e0ca-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="8e0ca-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="8e0ca-104">**logs** 节包含日志文件项，该项指定用于在 **DataFactory** 的操作期间记录错误的文件的名称。</span><span class="sxs-lookup"><span data-stu-id="8e0ca-104">The **logs** section contains a log file entry, which specifies the name of a file that records errors during the operation of the **DataFactory**.</span></span>

## <a name="syntax"></a><span data-ttu-id="8e0ca-105">语法</span><span class="sxs-lookup"><span data-stu-id="8e0ca-105">Syntax</span></span>

<span data-ttu-id="8e0ca-106">日志文件项的格式为：</span><span class="sxs-lookup"><span data-stu-id="8e0ca-106">A log file entry is of the form:</span></span>

`err=FileName`

<br/>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="8e0ca-107">部分</span><span class="sxs-lookup"><span data-stu-id="8e0ca-107">Part</span></span></p></th>
<th><p><span data-ttu-id="8e0ca-108">说明</span><span class="sxs-lookup"><span data-stu-id="8e0ca-108">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8e0ca-109"><strong>err</strong></span><span class="sxs-lookup"><span data-stu-id="8e0ca-109"><strong>err</strong></span></span></p></td>
<td><p><span data-ttu-id="8e0ca-110">字面字符串，用于指示这是日志文件项。</span><span class="sxs-lookup"><span data-stu-id="8e0ca-110">A literal string that indicates this is a log file entry.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e0ca-111"><em>FileName</em></span><span class="sxs-lookup"><span data-stu-id="8e0ca-111"><em>FileName</em></span></span></p></td>
<td><p><span data-ttu-id="8e0ca-p101">完整路径和文件名。典型的文件名是 <strong>c:\msdfmap.log</strong>。</span><span class="sxs-lookup"><span data-stu-id="8e0ca-p101">A complete path and file name. The typical file name is <strong>c:\msdfmap.log</strong>.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="8e0ca-114">日志文件将包含每个错误的用户名、HRESULT、日期和时间。</span><span class="sxs-lookup"><span data-stu-id="8e0ca-114">The log file will contain the user name, HRESULT, date, and time of each error.</span></span>

