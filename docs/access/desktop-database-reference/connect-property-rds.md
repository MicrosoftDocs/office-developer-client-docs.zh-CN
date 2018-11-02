---
title: Connect 属性 (RDS)
TOCTitle: Connect property (RDS)
ms:assetid: 11aa3284-18e9-6d2d-761b-c25090370b77
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248890(v=office.15)
ms:contentKeyID: 48543324
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: ebd9eb25e2e0e6b9b2233ff0d9faf8c3e369f0f9
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25925259"
---
# <a name="connect-property-rds"></a><span data-ttu-id="acd3f-102">Connect 属性 (RDS)</span><span class="sxs-lookup"><span data-stu-id="acd3f-102">Connect property (RDS)</span></span>


<span data-ttu-id="acd3f-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="acd3f-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="acd3f-104">指示在其中运行查询和更新操作的数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="acd3f-104">Indicates the database name from which the query and update operations are run.</span></span>

<span data-ttu-id="acd3f-105">可在设计时在 **RDS.DataControl** 对象的 OBJECT 标记中设置 [Connect](datacontrol-object-rds.md) 属性，或在运行时在脚本代码（例如，VBScript）中设置此属性。</span><span class="sxs-lookup"><span data-stu-id="acd3f-105">You can set the **Connect** property at design time in the [RDS.DataControl](datacontrol-object-rds.md) object's OBJECT tags, or at run time in scripting code (for instance, VBScript).</span></span>

## <a name="syntax"></a><span data-ttu-id="acd3f-106">语法</span><span class="sxs-lookup"><span data-stu-id="acd3f-106">Syntax</span></span>

<span data-ttu-id="acd3f-107">设计时：\<参数名称 ="连接"值 ="ConnectionString"\></span><span class="sxs-lookup"><span data-stu-id="acd3f-107">Design time: \<PARAM NAME="Connect" VALUE="ConnectionString"\></span></span>

<span data-ttu-id="acd3f-108">运行时间： DataControl.Connect ="ConnectionString"</span><span class="sxs-lookup"><span data-stu-id="acd3f-108">Run time: DataControl.Connect = "ConnectionString"</span></span>

## <a name="parameters"></a><span data-ttu-id="acd3f-109">参数</span><span class="sxs-lookup"><span data-stu-id="acd3f-109">Parameters</span></span>

- <span data-ttu-id="acd3f-110">*ConnectionString*</span><span class="sxs-lookup"><span data-stu-id="acd3f-110">*ConnectionString*</span></span>

  - <span data-ttu-id="acd3f-p101">有效的连接字符串。有关连接字符串的详细常规信息，请参阅 [ConnectionString](connectionstring-property-ado.md) 属性或提供程序文档。</span><span class="sxs-lookup"><span data-stu-id="acd3f-p101">A valid connection string. For more general information about connection strings, see the [ConnectionString](connectionstring-property-ado.md) property or your provider documentation.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="acd3f-p102">[!注释] 将 MS Remote 指定为 **RDS.DataControl** 的提供程序将创建一个四层方案。大于三层的方案均未经过测试，应该不会有此方面的需要。</span><span class="sxs-lookup"><span data-stu-id="acd3f-p102">Specifying MS Remote as the provider for the **RDS.DataControl** would create a four-tier scenario. Scenarios greater than three tiers have not been tested and should not be needed.</span></span>

- <span data-ttu-id="acd3f-115">*DataControl*</span><span class="sxs-lookup"><span data-stu-id="acd3f-115">*DataControl*</span></span>

  - <span data-ttu-id="acd3f-116">一个代表 **RDS.DataControl** 对象的对象变量。</span><span class="sxs-lookup"><span data-stu-id="acd3f-116">An object variable that represents an **RDS.DataControl** object.</span></span>

