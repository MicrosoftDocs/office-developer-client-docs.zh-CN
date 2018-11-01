---
title: Create 方法 (ADOX)
TOCTitle: Create Method (ADOX)
ms:assetid: d4072ee7-a0b9-7780-7be0-1d64b42b437c
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250060(v=office.15)
ms:contentKeyID: 48547924
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 91f5105611df85e007dea6d0e17e3104ea5987a3
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25870252"
---
# <a name="create-method-adox"></a><span data-ttu-id="c9203-102">Create 方法 (ADOX)</span><span class="sxs-lookup"><span data-stu-id="c9203-102">Create Method (ADOX)</span></span>


<span data-ttu-id="c9203-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="c9203-103">**Applies to**: Access 2013, Office 2013</span></span>


<span data-ttu-id="c9203-104">创建新目录。</span><span class="sxs-lookup"><span data-stu-id="c9203-104">Creates a new catalog.</span></span>

## <a name="syntax"></a><span data-ttu-id="c9203-105">语法</span><span class="sxs-lookup"><span data-stu-id="c9203-105">Syntax</span></span>

<span data-ttu-id="c9203-106">*目录*。创建*ConnectString*</span><span class="sxs-lookup"><span data-stu-id="c9203-106">*Catalog*.Create*ConnectString*</span></span>

## <a name="parameters"></a><span data-ttu-id="c9203-107">参数</span><span class="sxs-lookup"><span data-stu-id="c9203-107">Parameters</span></span>

  - <span data-ttu-id="c9203-108">*ConnectString*</span><span class="sxs-lookup"><span data-stu-id="c9203-108">*ConnectString*</span></span>

  - <span data-ttu-id="c9203-109">一个用来连接数据源的 **String** 值。</span><span class="sxs-lookup"><span data-stu-id="c9203-109">A **String** value used to connect to the data source.</span></span>

## <a name="remarks"></a><span data-ttu-id="c9203-110">说明</span><span class="sxs-lookup"><span data-stu-id="c9203-110">Remarks</span></span>

<span data-ttu-id="c9203-p101">**Create** 方法创建一个新 ADO [Connection](connection-object-ado.md) 并打开它，该对象连接到在 *ConnectString* 中指定的数据源。如果成功，该新 **Connection** 对象将被分配给 [ActiveConnection](activeconnection-property-adox.md) 属性。</span><span class="sxs-lookup"><span data-stu-id="c9203-p101">The **Create** method creates and opens a new ADO [Connection](connection-object-ado.md) to the data source specified in *ConnectString*. If successful, the new **Connection** object is assigned to the [ActiveConnection](activeconnection-property-adox.md) property.</span></span>

<span data-ttu-id="c9203-113">如果提供程序不支持创建新目录，则会发生错误。</span><span class="sxs-lookup"><span data-stu-id="c9203-113">An error will occur if the provider does not support creating new catalogs.</span></span>

