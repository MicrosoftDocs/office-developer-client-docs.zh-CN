---
title: Create 方法 (ADOX)
TOCTitle: Create method (ADOX)
ms:assetid: d4072ee7-a0b9-7780-7be0-1d64b42b437c
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250060(v=office.15)
ms:contentKeyID: 48547924
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: e98854665185d682b9049b000bf4b600040ba624
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32295420"
---
# <a name="create-method-adox"></a><span data-ttu-id="3e96e-102">Create 方法 (ADOX)</span><span class="sxs-lookup"><span data-stu-id="3e96e-102">Create method (ADOX)</span></span>

<span data-ttu-id="3e96e-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="3e96e-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="3e96e-104">创建新目录。</span><span class="sxs-lookup"><span data-stu-id="3e96e-104">Creates a new catalog.</span></span>

## <a name="syntax"></a><span data-ttu-id="3e96e-105">语法</span><span class="sxs-lookup"><span data-stu-id="3e96e-105">Syntax</span></span>

<span data-ttu-id="3e96e-106">*目录*。创建*ConnectString*</span><span class="sxs-lookup"><span data-stu-id="3e96e-106">*Catalog*.Create*ConnectString*</span></span>

## <a name="parameters"></a><span data-ttu-id="3e96e-107">参数</span><span class="sxs-lookup"><span data-stu-id="3e96e-107">Parameters</span></span>

|<span data-ttu-id="3e96e-108">参数</span><span class="sxs-lookup"><span data-stu-id="3e96e-108">Parameter</span></span>|<span data-ttu-id="3e96e-109">描述</span><span class="sxs-lookup"><span data-stu-id="3e96e-109">Description</span></span>|
|:--------|:----------|
|<span data-ttu-id="3e96e-110">*ConnectString*</span><span class="sxs-lookup"><span data-stu-id="3e96e-110">*ConnectString*</span></span> |<span data-ttu-id="3e96e-111">一个用来连接数据源的 **String** 值。</span><span class="sxs-lookup"><span data-stu-id="3e96e-111">A **String** value used to connect to the data source.</span></span>|

## <a name="remarks"></a><span data-ttu-id="3e96e-112">注解</span><span class="sxs-lookup"><span data-stu-id="3e96e-112">Remarks</span></span>

<span data-ttu-id="3e96e-p101">**Create** 方法创建一个新 ADO [Connection](connection-object-ado.md) 并打开它，该对象连接到在 *ConnectString* 中指定的数据源。如果成功，该新 **Connection** 对象将被分配给 [ActiveConnection](activeconnection-property-adox.md) 属性。</span><span class="sxs-lookup"><span data-stu-id="3e96e-p101">The **Create** method creates and opens a new ADO [Connection](connection-object-ado.md) to the data source specified in *ConnectString*. If successful, the new **Connection** object is assigned to the [ActiveConnection](activeconnection-property-adox.md) property.</span></span>

<span data-ttu-id="3e96e-115">如果提供程序不支持创建新目录，则会发生错误。</span><span class="sxs-lookup"><span data-stu-id="3e96e-115">An error will occur if the provider does not support creating new catalogs.</span></span>

