---
title: Create 方法 (ADOX)
TOCTitle: Create method (ADOX)
ms:assetid: d4072ee7-a0b9-7780-7be0-1d64b42b437c
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250060(v=office.15)
ms:contentKeyID: 48547924
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 866faae5d8c99258075a81f504fa9ce069f4690a
ms.sourcegitcommit: 980a96cf444882d3d34cecb5faac8f8a7b7c4b57
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2018
ms.locfileid: "25949374"
---
# <a name="create-method-adox"></a><span data-ttu-id="ba196-102">Create 方法 (ADOX)</span><span class="sxs-lookup"><span data-stu-id="ba196-102">Create method (ADOX)</span></span>

<span data-ttu-id="ba196-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="ba196-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="ba196-104">创建新目录。</span><span class="sxs-lookup"><span data-stu-id="ba196-104">Creates a new catalog.</span></span>

## <a name="syntax"></a><span data-ttu-id="ba196-105">语法</span><span class="sxs-lookup"><span data-stu-id="ba196-105">Syntax</span></span>

<span data-ttu-id="ba196-106">*目录*。创建*ConnectString*</span><span class="sxs-lookup"><span data-stu-id="ba196-106">*Catalog*.Create*ConnectString*</span></span>

## <a name="parameters"></a><span data-ttu-id="ba196-107">参数</span><span class="sxs-lookup"><span data-stu-id="ba196-107">Parameters</span></span>

|<span data-ttu-id="ba196-108">参数</span><span class="sxs-lookup"><span data-stu-id="ba196-108">Parameter</span></span>|<span data-ttu-id="ba196-109">说明</span><span class="sxs-lookup"><span data-stu-id="ba196-109">Description</span></span>|
|:--------|:----------|
|<span data-ttu-id="ba196-110">*ConnectString*</span><span class="sxs-lookup"><span data-stu-id="ba196-110">*ConnectString*</span></span> |<span data-ttu-id="ba196-111">一个用来连接数据源的 **String** 值。</span><span class="sxs-lookup"><span data-stu-id="ba196-111">A **String** value used to connect to the data source.</span></span>|

## <a name="remarks"></a><span data-ttu-id="ba196-112">说明</span><span class="sxs-lookup"><span data-stu-id="ba196-112">Remarks</span></span>

<span data-ttu-id="ba196-p101">**Create** 方法创建一个新 ADO [Connection](connection-object-ado.md) 并打开它，该对象连接到在 *ConnectString* 中指定的数据源。如果成功，该新 **Connection** 对象将被分配给 [ActiveConnection](activeconnection-property-adox.md) 属性。</span><span class="sxs-lookup"><span data-stu-id="ba196-p101">The **Create** method creates and opens a new ADO [Connection](connection-object-ado.md) to the data source specified in *ConnectString*. If successful, the new **Connection** object is assigned to the [ActiveConnection](activeconnection-property-adox.md) property.</span></span>

<span data-ttu-id="ba196-115">如果提供程序不支持创建新目录，则会发生错误。</span><span class="sxs-lookup"><span data-stu-id="ba196-115">An error will occur if the provider does not support creating new catalogs.</span></span>

