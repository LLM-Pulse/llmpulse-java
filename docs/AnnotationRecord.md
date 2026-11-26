

# AnnotationRecord


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**id** | **Integer** |  |  |
|**title** | **String** |  |  |
|**description** | **String** |  |  |
|**annotationDate** | **LocalDate** |  |  |
|**color** | **String** |  |  |
|**category** | **String** | user (written by a person) or system (added by the platform) |  |
|**origin** | **String** | manual, platform (a platform-wide event) or automation (a project change recorded automatically) |  |
|**annotationCategory** | [**AnnotationRecordAnnotationCategory**](AnnotationRecordAnnotationCategory.md) |  |  |
|**editable** | **Boolean** | Whether the requesting user may update or delete it |  |
|**createdAt** | **OffsetDateTime** |  |  |



