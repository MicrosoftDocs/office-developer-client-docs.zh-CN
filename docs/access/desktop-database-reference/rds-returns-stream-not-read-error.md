---
title: RDS 返回“Stream Not Read”错误
TOCTitle: RDS Returns "Stream Not Read" Error
ms:assetid: 325f7b9d-8e71-bc2c-94e3-b4b4a1a2dc58
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249097(v=office.15)
ms:contentKeyID: 48544075
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: a9b3372db2ff86ea2af401720ba091100d4cfce1
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25468818"
---
# <a name="rds-returns-stream-not-read-error"></a><span data-ttu-id="a4966-102">RDS 返回\"Stream Not Read\"错误</span><span class="sxs-lookup"><span data-stu-id="a4966-102">RDS Returns \"Stream Not Read\" Error</span></span>


<span data-ttu-id="a4966-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="a4966-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="a4966-p101">“The Stream object could not be read because it is empty, or the current position is at the end of the Stream. For non-empty Streams, set the current position with the Position property. To determine if a Stream is empty, check the Size property.”</span><span class="sxs-lookup"><span data-stu-id="a4966-p101">"The Stream object could not be read because it is empty, or the current position is at the end of the Stream. For non-empty Streams, set the current position with the Position property. To determine if a Stream is empty, check the Size property."</span></span>

<span data-ttu-id="a4966-p102">如果您获得上面的错误，则可能是由于您尝试通过 http 使用参数化分层查询。RDS 不允许您远程使用参数化层次结构。</span><span class="sxs-lookup"><span data-stu-id="a4966-p102">If you get the error above, it may be a result of trying to use a parameterized hierarchical query over http. RDS does not permit you to remote parameterized hierarchies.</span></span>

