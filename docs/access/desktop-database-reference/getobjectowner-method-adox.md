---
title: GetObjectOwner 方法 (ADOX)
TOCTitle: GetObjectOwner Method (ADOX)
ms:assetid: 716dd49a-8663-3f7a-32a3-0be353aea506
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249451(v=office.15)
ms:contentKeyID: 48545585
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: e20141e379cb207819744fd65b78abf7d2d15712
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25468575"
---
# <a name="getobjectowner-method-adox"></a><span data-ttu-id="03016-102">GetObjectOwner 方法 (ADOX)</span><span class="sxs-lookup"><span data-stu-id="03016-102">GetObjectOwner Method (ADOX)</span></span>


<span data-ttu-id="03016-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="03016-103">**Applies to**: Access 2013 | Office 2013</span></span>


<span data-ttu-id="03016-104">返回 [Catalog](catalog-object-adox.md) 中某个对象的所有者。</span><span class="sxs-lookup"><span data-stu-id="03016-104">Returns the owner of an object in a [Catalog](catalog-object-adox.md).</span></span>

## <a name="syntax"></a><span data-ttu-id="03016-105">语法</span><span class="sxs-lookup"><span data-stu-id="03016-105">Syntax</span></span>

<span data-ttu-id="03016-106">*所有者* = *目录*。GetObjectOwner (*ObjectName*、 *ObjectType* \[，*ObjectTypeId*\])</span><span class="sxs-lookup"><span data-stu-id="03016-106">*Owner* = *Catalog*.GetObjectOwner(*ObjectName*, *ObjectType* \[,*ObjectTypeId*\])</span></span>

## <a name="return-value"></a><span data-ttu-id="03016-107">返回值</span><span class="sxs-lookup"><span data-stu-id="03016-107">Return Value</span></span>

<span data-ttu-id="03016-108">返回一个 **String** 值，该值指定拥有该对象的 [User](name-property-adox.md) 或 [Group](user-object-adox.md) 的 [Name](group-object-adox.md)。</span><span class="sxs-lookup"><span data-stu-id="03016-108">Returns a **String** value that specifies the [Name](name-property-adox.md) of the [User](user-object-adox.md) or [Group](group-object-adox.md) that owns the object.</span></span>

## <a name="parameters"></a><span data-ttu-id="03016-109">参数</span><span class="sxs-lookup"><span data-stu-id="03016-109">Parameters</span></span>

  - <span data-ttu-id="03016-110">*ObjectName*</span><span class="sxs-lookup"><span data-stu-id="03016-110">*ObjectName*</span></span>

  - <span data-ttu-id="03016-111">**String** 值，指定返回所有者的对象的名称。</span><span class="sxs-lookup"><span data-stu-id="03016-111">A **String** value that specifies the name of the object for which to return the owner.</span></span>

  - <span data-ttu-id="03016-112">*ObjectType*</span><span class="sxs-lookup"><span data-stu-id="03016-112">*ObjectType*</span></span>

  - <span data-ttu-id="03016-113">一个可设为某一 **ObjectTypeEnum** 常量的 [Long](objecttypeenum.md) 值，指定获得其所有者的对象的类型。</span><span class="sxs-lookup"><span data-stu-id="03016-113">A **Long** value which can be one of the [ObjectTypeEnum](objecttypeenum.md) constants, that specifies the type of the object for which to get the owner.</span></span>

  - <span data-ttu-id="03016-114">*ObjectTypeId*</span><span class="sxs-lookup"><span data-stu-id="03016-114">*ObjectTypeId*</span></span>

  - <span data-ttu-id="03016-115">可选。</span><span class="sxs-lookup"><span data-stu-id="03016-115">Optional.</span></span> <span data-ttu-id="03016-116">**Variant** 值，指定 OLE DB 规范未定义的提供程序对象类型的 GUID。</span><span class="sxs-lookup"><span data-stu-id="03016-116">A **Variant** value that specifies the GUID for a provider object type not defined by the OLE DB specification.</span></span> <span data-ttu-id="03016-117">此参数是必需的如果将*ObjectType*设置为**adPermObjProviderSpecific**;否则，它将不使用。</span><span class="sxs-lookup"><span data-stu-id="03016-117">This parameter is required if *ObjectType* is set to **adPermObjProviderSpecific**; otherwise, it is not used.</span></span>

## <a name="remarks"></a><span data-ttu-id="03016-118">备注</span><span class="sxs-lookup"><span data-stu-id="03016-118">Remarks</span></span>

<span data-ttu-id="03016-119">如果提供程序不支持返回对象所有者，则会发生错误。</span><span class="sxs-lookup"><span data-stu-id="03016-119">An error will occur if the provider does not support returning object owners.</span></span>
