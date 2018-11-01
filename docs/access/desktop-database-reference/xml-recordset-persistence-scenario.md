---
title: XML Recordset 持久化方案
TOCTitle: XML Recordset Persistence Scenario
ms:assetid: 08f464da-10ba-b649-7571-766a40da2e04
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248825(v=office.15)
ms:contentKeyID: 48543107
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: fbf60cf8ef6099f8d16ab20f4441477fad1d32ab
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/01/2018
ms.locfileid: "25891168"
---
# <a name="xml-recordset-persistence-scenario"></a><span data-ttu-id="83aea-102">XML 记录集暂留方案</span><span class="sxs-lookup"><span data-stu-id="83aea-102">XML Recordset Persistence Scenario</span></span>

<span data-ttu-id="83aea-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="83aea-103">**Applies to**: Access 2013, Office 2013</span></span>

## <a name="xml-recordset-persistence-scenario"></a><span data-ttu-id="83aea-104">XML 记录集暂留方案</span><span class="sxs-lookup"><span data-stu-id="83aea-104">XML Recordset Persistence Scenario</span></span>

<span data-ttu-id="83aea-105">在该方案中，您将创建一个 Active Server Pages (ASP) 应用程序，该应用程序将 **Recordset** 对象的内容直接保存到 ASP **Response** 对象中。</span><span class="sxs-lookup"><span data-stu-id="83aea-105">In this scenario, you will create an Active Server Pages (ASP) application that saves the contents of a **Recordset** object directly to the ASP **Response** object.</span></span>

> [!NOTE]
> <span data-ttu-id="83aea-106">[!注释] 该方案要求您的服务器上装有 Internet Information Server 5.0 (IIS) 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="83aea-106">This scenario requires that your server have Internet Information Server 5.0 (IIS) or later installed.</span></span>

<span data-ttu-id="83aea-107">返回的 **Recordset** 使用 [RDS.DataControl](datacontrol-object-rds.md) 显示在 Internet Explorer 中。</span><span class="sxs-lookup"><span data-stu-id="83aea-107">The returned **Recordset** is displayed in Internet Explorer using an [RDS.DataControl](datacontrol-object-rds.md).</span></span>

<span data-ttu-id="83aea-108">下列步骤是创建该方案所必需的步骤：</span><span class="sxs-lookup"><span data-stu-id="83aea-108">The following steps are necessary to create this scenario:</span></span>

1.  <span data-ttu-id="83aea-109">设置应用程序。</span><span class="sxs-lookup"><span data-stu-id="83aea-109">Set up the application.</span></span>

2.  <span data-ttu-id="83aea-110">获取数据。</span><span class="sxs-lookup"><span data-stu-id="83aea-110">Get the data.</span></span>

3.  <span data-ttu-id="83aea-111">发送数据。</span><span class="sxs-lookup"><span data-stu-id="83aea-111">Send the data.</span></span>

4.  <span data-ttu-id="83aea-112">接收和显示数据。</span><span class="sxs-lookup"><span data-stu-id="83aea-112">Receive and display the data.</span></span>

### <a name="next-step"></a><span data-ttu-id="83aea-113">后续步骤</span><span class="sxs-lookup"><span data-stu-id="83aea-113">Next step</span></span>

[<span data-ttu-id="83aea-114">步骤 1：设置应用程序</span><span class="sxs-lookup"><span data-stu-id="83aea-114">Step 1: Set Up the Application</span></span>](step-1-set-up-the-application.md)

