---
title: GetObjectOwner 方法 (ADOX)
TOCTitle: GetObjectOwner Method (ADOX)
ms:assetid: 716dd49a-8663-3f7a-32a3-0be353aea506
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249451(v=office.15)
ms:contentKeyID: 48545585
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 6e6c2432370f2480484cf1165249bc8573b27372
ms.sourcegitcommit: a49b77f4c8cec69f90656a86f0872cf34c35968e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2018
ms.locfileid: "25603110"
---
# <a name="getobjectowner-method-adox"></a><span data-ttu-id="a750d-102">GetObjectOwner 方法 (ADOX)</span><span class="sxs-lookup"><span data-stu-id="a750d-102">GetObjectOwner Method (ADOX)</span></span>


<span data-ttu-id="a750d-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="a750d-103">**Applies to**: Access 2013 | Office 2013</span></span>


<span data-ttu-id="a750d-104">返回 [Catalog](catalog-object-adox.md) 中某个对象的所有者。</span><span class="sxs-lookup"><span data-stu-id="a750d-104">Returns the owner of an object in a [Catalog](catalog-object-adox.md).</span></span>

## <a name="syntax"></a><span data-ttu-id="a750d-105">语法</span><span class="sxs-lookup"><span data-stu-id="a750d-105">Syntax</span></span>

<span data-ttu-id="a750d-106">*所有者* = *目录*。GetObjectOwner (*ObjectName*、 *ObjectType* \[，*ObjectTypeId*\])</span><span class="sxs-lookup"><span data-stu-id="a750d-106">*Owner* = *Catalog*.GetObjectOwner(*ObjectName*, *ObjectType* \[,*ObjectTypeId*\])</span></span>

<span data-ttu-id="a750d-107"><<<<<<< 标头</span><span class="sxs-lookup"><span data-stu-id="a750d-107"><<<<<<< HEAD</span></span>
## <a name="return-value"></a><span data-ttu-id="a750d-108">返回值</span><span class="sxs-lookup"><span data-stu-id="a750d-108">Return Value</span></span>
=======
## <a name="return-value"></a><span data-ttu-id="a750d-109">返回值</span><span class="sxs-lookup"><span data-stu-id="a750d-109">Return value</span></span>
>>>>>>> <span data-ttu-id="a750d-110">master</span><span class="sxs-lookup"><span data-stu-id="a750d-110">master</span></span>

<span data-ttu-id="a750d-111">返回一个 **String** 值，该值指定拥有该对象的 [User](name-property-adox.md) 或 [Group](user-object-adox.md) 的 [Name](group-object-adox.md)。</span><span class="sxs-lookup"><span data-stu-id="a750d-111">Returns a **String** value that specifies the [Name](name-property-adox.md) of the [User](user-object-adox.md) or [Group](group-object-adox.md) that owns the object.</span></span>

## <a name="parameters"></a><span data-ttu-id="a750d-112">参数</span><span class="sxs-lookup"><span data-stu-id="a750d-112">Parameters</span></span>

  - <span data-ttu-id="a750d-113">*ObjectName*</span><span class="sxs-lookup"><span data-stu-id="a750d-113">*ObjectName*</span></span>

  - <span data-ttu-id="a750d-114">**String** 值，指定返回所有者的对象的名称。</span><span class="sxs-lookup"><span data-stu-id="a750d-114">A **String** value that specifies the name of the object for which to return the owner.</span></span>

  - <span data-ttu-id="a750d-115">*ObjectType*</span><span class="sxs-lookup"><span data-stu-id="a750d-115">*ObjectType*</span></span>

  - <span data-ttu-id="a750d-116">一个可设为某一 **ObjectTypeEnum** 常量的 [Long](objecttypeenum.md) 值，指定获得其所有者的对象的类型。</span><span class="sxs-lookup"><span data-stu-id="a750d-116">A **Long** value which can be one of the [ObjectTypeEnum](objecttypeenum.md) constants, that specifies the type of the object for which to get the owner.</span></span>

  - <span data-ttu-id="a750d-117">*ObjectTypeId*</span><span class="sxs-lookup"><span data-stu-id="a750d-117">*ObjectTypeId*</span></span>

  - <span data-ttu-id="a750d-118">可选。</span><span class="sxs-lookup"><span data-stu-id="a750d-118">Optional.</span></span> <span data-ttu-id="a750d-119">**Variant** 值，指定 OLE DB 规范未定义的提供程序对象类型的 GUID。</span><span class="sxs-lookup"><span data-stu-id="a750d-119">A **Variant** value that specifies the GUID for a provider object type not defined by the OLE DB specification.</span></span> <span data-ttu-id="a750d-120">此参数是必需的如果将*ObjectType*设置为**adPermObjProviderSpecific**;否则，它将不使用。</span><span class="sxs-lookup"><span data-stu-id="a750d-120">This parameter is required if *ObjectType* is set to **adPermObjProviderSpecific**; otherwise, it is not used.</span></span>

## <a name="remarks"></a><span data-ttu-id="a750d-121">备注</span><span class="sxs-lookup"><span data-stu-id="a750d-121">Remarks</span></span>

<span data-ttu-id="a750d-122">如果提供程序不支持返回对象所有者，则会发生错误。</span><span class="sxs-lookup"><span data-stu-id="a750d-122">An error will occur if the provider does not support returning object owners.</span></span>

