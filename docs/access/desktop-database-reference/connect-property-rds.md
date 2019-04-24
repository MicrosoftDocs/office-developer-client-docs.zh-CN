---
title: Connect 属性 (RDS)
TOCTitle: Connect property (RDS)
ms:assetid: 11aa3284-18e9-6d2d-761b-c25090370b77
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248890(v=office.15)
ms:contentKeyID: 48543324
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 42e7dd643985cee9aef8887099eb90dcdb381f4e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32295980"
---
# <a name="connect-property-rds"></a><span data-ttu-id="ff11f-102">Connect 属性 (RDS)</span><span class="sxs-lookup"><span data-stu-id="ff11f-102">Connect property (RDS)</span></span>

<span data-ttu-id="ff11f-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="ff11f-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="ff11f-104">指示在其中运行查询和更新操作的数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="ff11f-104">Indicates the database name from which the query and update operations are run.</span></span>

<span data-ttu-id="ff11f-105">可在设计时在 [RDS.DataControl](datacontrol-object-rds.md) 对象的 OBJECT 标记中设置 **Connect** 属性，或在运行时在脚本代码（例如，VBScript）中设置此属性。</span><span class="sxs-lookup"><span data-stu-id="ff11f-105">You can set the **Connect** property at design time in the [RDS.DataControl](datacontrol-object-rds.md) object's OBJECT tags, or at run time in scripting code (for instance, VBScript).</span></span>

## <a name="syntax"></a><span data-ttu-id="ff11f-106">语法</span><span class="sxs-lookup"><span data-stu-id="ff11f-106">Syntax</span></span>

<span data-ttu-id="ff11f-107">设计时: \<PARAM 名称 = "Connect" VALUE = "ConnectionString"\></span><span class="sxs-lookup"><span data-stu-id="ff11f-107">Design time: \<PARAM NAME="Connect" VALUE="ConnectionString"\></span></span>

<span data-ttu-id="ff11f-108">运行时间: rds.datacontrol = "ConnectionString"</span><span class="sxs-lookup"><span data-stu-id="ff11f-108">Run time: DataControl.Connect = "ConnectionString"</span></span>

## <a name="parameters"></a><span data-ttu-id="ff11f-109">参数</span><span class="sxs-lookup"><span data-stu-id="ff11f-109">Parameters</span></span>

|<span data-ttu-id="ff11f-110">参数</span><span class="sxs-lookup"><span data-stu-id="ff11f-110">Parameter</span></span>|<span data-ttu-id="ff11f-111">描述</span><span class="sxs-lookup"><span data-stu-id="ff11f-111">Description</span></span>|
|:--------|:----------|
|<span data-ttu-id="ff11f-112">*ConnectionString*</span><span class="sxs-lookup"><span data-stu-id="ff11f-112">*ConnectionString*</span></span> |<span data-ttu-id="ff11f-p101">有效的连接字符串。有关连接字符串的详细常规信息，请参阅 [ConnectionString](connectionstring-property-ado.md) 属性或提供程序文档。</span><span class="sxs-lookup"><span data-stu-id="ff11f-p101">A valid connection string. For more general information about connection strings, see the [ConnectionString](connectionstring-property-ado.md) property or your provider documentation.</span></span><br/><br/><span data-ttu-id="ff11f-115">**注意**: 指定 MS Remote 作为 RDS 的提供程序 **。rds.datacontrol**将创建一个四层方案。</span><span class="sxs-lookup"><span data-stu-id="ff11f-115">**NOTE**: Specifying MS Remote as the provider for the **RDS.DataControl** would create a four-tier scenario.</span></span> <span data-ttu-id="ff11f-116">大于三层的方案均未经过测试，应该不会有此方面的需要。</span><span class="sxs-lookup"><span data-stu-id="ff11f-116">Scenarios greater than three tiers have not been tested and should not be needed.</span></span>|
|<span data-ttu-id="ff11f-117">*DataControl*</span><span class="sxs-lookup"><span data-stu-id="ff11f-117">*DataControl*</span></span> |<span data-ttu-id="ff11f-118">一个代表 **RDS.DataControl** 对象的对象变量。</span><span class="sxs-lookup"><span data-stu-id="ff11f-118">An object variable that represents an **RDS.DataControl** object.</span></span>|

