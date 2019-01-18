---
title: InternetTimeout 属性 (RDS)
TOCTitle: InternetTimeout property (RDS)
ms:assetid: 66fc6e87-3d23-ce2c-18f5-0fc83ac43801
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249401(v=office.15)
ms:contentKeyID: 48545353
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 8c0650a287e2aebc13b89572db112b8f9b333dc6
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28710074"
---
# <a name="internettimeout-property-rds"></a><span data-ttu-id="2b47e-102">InternetTimeout 属性 (RDS)</span><span class="sxs-lookup"><span data-stu-id="2b47e-102">InternetTimeout property (RDS)</span></span>


<span data-ttu-id="2b47e-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="2b47e-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="2b47e-104">指示请求超时前等待的毫秒数。</span><span class="sxs-lookup"><span data-stu-id="2b47e-104">Indicates the number of milliseconds to wait before a request times out.</span></span>

## <a name="settings-and-return-values"></a><span data-ttu-id="2b47e-105">设置和返回值</span><span class="sxs-lookup"><span data-stu-id="2b47e-105">Settings and return values</span></span>

<span data-ttu-id="2b47e-106">设置或返回一个 **Long** 值，该值表示请求超时前等待的毫秒数。</span><span class="sxs-lookup"><span data-stu-id="2b47e-106">Sets or returns a **Long** value that represents the number of milliseconds before a request will time out.</span></span>

## <a name="remarks"></a><span data-ttu-id="2b47e-107">备注</span><span class="sxs-lookup"><span data-stu-id="2b47e-107">Remarks</span></span>

<span data-ttu-id="2b47e-108">此属性仅适用于通过 HTTP 或 HTTPS 协议发送的请求。</span><span class="sxs-lookup"><span data-stu-id="2b47e-108">This property applies only to requests sent with the HTTP or HTTPS protocols.</span></span>

<span data-ttu-id="2b47e-p101">执行三层环境中的请求可能需要几分钟的时间。使用此属性可为长时间运行的请求指定附加时间。</span><span class="sxs-lookup"><span data-stu-id="2b47e-p101">Requests in a three-tier environment can take several minutes to execute. Use this property to specify additional time for long-running requests.</span></span>

