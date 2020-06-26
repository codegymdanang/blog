---
layout: blog
title: Tổng hợp JPA Annotation
slug : tong-hop-jpa-annotation
category: laptrinhspring
tags: []
summery: Tổng hợp JPA Annotation
image: /images/blog/spring.png
description : webservice là gì , hướng dẫn webservice , ví dụ webservice , soap là gì , restful webservice là gì
youtubeId: WNfuVJptPnQ
---

# **Giới thiệu nội dung bài viết**

Chào các em ,chủ để hôm nay chúng ta sẽ tìm hiểu về các annotation mà JPA cung cấp cho chúng ta
Nội dung mình sẽ giải thích trong bài này sẽ xoay quanh các chủ đề sau đây.


1. @Access
The @Access annotation is used to specify the access type of the associated entity class, mapped superclass, or the embeddable class and entity attribute.

2. @AssociationOverride
The @AssociationOverride annotation is used to override an association mapping (e.g.  @ManyToOne, @OneToOne, @OneToMany, @ManyToMany) inherited from a mapped superclass or an embeddable.

3. @AssociationOverrides
The @AssociationOverrides is used to group several @AssociationOverride annotations.

4. @AttributeOverride
The @AttributeOverride annotation is used to override an attribute mapping inherited from a mapped superclass or an embeddable.

5. @AttributeOverrides
The @AttributeOverrides is used to group several @AttributeOverride annotations.

6. @Basic
The @Basic annotation is used to map a basic attribute type to a database column.

7. @Cacheable
The @Cacheable annotation is used to specify whether an entity should be stored in the second-level cache.

8. @CollectionTable
The @CollectionTable annotation is used to specify the database table that stores the values of a basic or an embeddable type collection.

9. @Column
The @Column annotation is used to specify the mapping between a basic entity attribute and the database table column.

10. @ColumnResult
The @ColumnResult annotation is used in conjunction with the @SqlResultSetMapping or @ConstructorResult annotations to map a SQL column for a given SELECT query.

11. @ConstructorResult
The @ConstructorResult annotation is used in conjunction with the @SqlResultSetMapping annotations to map columns of a given SELECT query to a certain object constructor.

12. @Convert
The @Convert annotation is used to specify the AttributeConverter implementation used to convert the currently annotated basic attribute.

13. @Converter
The @Converter annotation is used to specify that the current annotate AttributeConverter implementation can be used as a JPA basic attribute converter.

14. @Converts
The @Converts annotation is used to group multiple @Convert annotations.

15. @DiscriminatorColumn
The @DiscriminatorColumn annotation is used to specify the discriminator column name and the discriminator type for the SINGLE_TABLE and JOINED Inheritance strategies.

16. @DiscriminatorValue
The @DiscriminatorValue annotation is used to specify what value of the discriminator column is used for mapping the currently annotated entity.

17. @ElementCollection
The @ElementCollection annotation is used to specify a collection of basic or embeddable types.

18. @Embeddable
The @Embeddable annotation is used to specify embeddable types. Like basic types, embeddable types do not have any identity, being managed by their owning entity

19. @Embedded
The @Embedded annotation is used to specify that a given entity attribute represents an embeddable type.

20. @EmbeddedId
The @EmbeddedId annotation is used to specify the entity identifier is an embeddable type.

21. @Entity
The @Entity annotation is used to specify that the currently annotate class represents an entity type. Unlike basic and embeddable types, entity types have an identity and their state is managed by the underlying Persistence Context.

22. @EntityListeners
The @EntityListeners annotation is used to specify an array of callback listener classes that are used by the currently annotated entity.

23. @EntityResult
The @EntityResult annotation is used with the @SqlResultSetMapping annotation to map the selected columns to an entity.

24. @Enumerated
The @Enumerated annotation is used to specify that an entity attribute represents an enumerated type.

25. @ExcludeDefaultListeners
The @ExcludeDefaultListeners annotation is used to specify that the currently annotated entity skips the invocation of any default listener.

26. @ExcludeSuperclassListeners
The @ExcludeSuperclassListeners annotation is used to specify that the currently annotated entity skips the invocation of listeners declared by its superclass.

27. @FieldResult
The @FieldResult annotation is used with the @EntityResult annotation to map the selected columns to the fields of some specific entity.

28. @ForeignKey
The @ForeignKey annotation is used to specify the associated foreign key of a @JoinColumn mapping. The @ForeignKeyannotation is only used if the automated schema generation tool is enabled. In which case, it allows you to customize the underlying foreign key definition.

29. @GeneratedValue
The @GeneratedValue annotation specifies that the entity identifier value is automatically generated using an identity column, a database sequence, or a table generator. Hibernate supports the @GeneratedValue mapping even for UUIDidentifiers.

30. @Id
The @Id annotation specifies the entity identifier. An entity must always have an identifier attribute, which is used when loading the entity in a given Persistence Context

31. @IdClass
The @IdClass annotation is used if the current entity defined a composite identifier. A separate class encapsulates all the identifier attributes, which are mirrored by the current entity mapping.

32. @Index
The @Index annotation is used by the automated schema generation tool to create a database index.

33. @Inheritance
The @Inheritance annotation is used to specify the inheritance strategy of a given entity class hierarchy.

34. @JoinColumn
The @JoinColumn annotation is used to specify the FOREIGN KEY column used when joining an entity association or an embeddable collection.

35. @JoinColumns
The @JoinColumns annotation is used to group multiple @JoinColumn annotations, which are used when mapping entity association or an embeddable collection using a composite identifier

36. @JoinTable
The @JoinTable annotation is used to specify the link table between two other database tables.

37. @Lob
The @Lob annotation is used to specify that the currently annotated entity attribute represents a large object type.

38. @ManyToMany
The @ManyToMany annotation is used to specify a many-to-many database relationship.

39. @ManyToOne
The @ManyToOne annotation is used to specify a many-to-one database relationship.

40. @MapKey
The @MapKey annotation is used to specify the key of a java.util.Map association for which the key type is either the primary key or an attribute of the entity that represents the value of the map.

41. @MapKeyClass
The @MapKeyClass annotation is used to specify the type of the map key of a java.util.Map associations.

42. @MapKeyColumn
The @MapKeyColumn annotation is used to specify the database column, which stores the key of a java.util.Mapassociation for which the map key is a basic type.

43. @MapKeyEnumerated
The @MapKeyEnumerated annotation is used to specify that the key of java.util.Map association is a Java Enum.

44. @MapKeyJoinColumn
The @MapKeyJoinColumn annotation is used to specify that the key of java.util.Map association is an entity association. The map key column is a FOREIGN KEY in a link table that also joins the Map owner’s table with the table where the Map value resides.

45. @MapKeyJoinColumns
The @MapKeyJoinColumns annotation is used to group several @MapKeyJoinColumn mappings when the java.util.Map association key uses a composite identifier.

46. @MapKeyTemporal
The @MapKeyTemporal annotation is used to specify that the key of java.util.Map association is a @TemporalType (e.g. DATE, TIME, TIMESTAMP).

47. @MappedSuperclass
The @MappedSuperclass annotation is used to specify that the currently annotated type attributes are inherited by any subclass entity.

48. @MapsId
The @MapsId annotation is used to specify that the entity identifier is mapped by the currently annotated @ManyToOne or @OneToOne association.

49. @NamedAttributeNode
The @NamedAttributeNode annotation is used to specify each individual attribute node that needs to be fetched by an Entity Graph.

50. @NamedEntityGraph
The @NamedEntityGraph annotation is used to specify an Entity Graph that can be used by an entity query to override the default fetch plan.

51. @NamedEntityGraphs
The @NamedEntityGraphs annotation is used to group multiple @NamedEntityGraph annotations.

52. @NamedNativeQueries
The @NamedNativeQueries annotation is used to group multiple @NamedNativeQuery annotations.

53. @NamedNativeQuery
The @NamedNativeQuery annotation is used to specify a native SQL query that can be retrieved later by its name.

54. @NamedQueries
The @NamedQueries annotation is used to group multiple @NamedQuery annotations.

55. @NamedQuery
The @NamedQuery annotation is used to specify a JPQL query that can be retrieved later by its name.

56. @NamedStoredProcedureQueries
The @NamedStoredProcedureQueries annotation is used to group

57. @NamedStoredProcedureQuery
The @NamedStoredProcedureQuery annotation is used to specify a stored procedure query that can be retrieved later by its name

58. @NamedSubgraph
The @NamedSubgraph annotation used to specify a subgraph in an Entity Graph.

59. @OneToMany
The @OneToMany annotation is used to specify a one-to-many database relationship.

60. @OneToOne
The @OneToOne annotation is used to specify a one-to-one database relationship.

61. @OrderBy
The @OrderBy annotation is used to specify the entity attributes used for sorting when fetching the currently annotated collection.

62. @OrderColumn
The @OrderColumn annotation is used to specify that the current annotation collection order should be materialized in the database.

63. @PersistenceContext
The @PersistenceContext annotation is used to specify the EntityManager that needs to be injected as a dependency.

64. @PersistenceContexts
The @PersistenceContexts annotation is used to group multiple @PersistenceContext annotations.

65. @PersistenceProperty
The @PersistenceProperty annotation is used by the @PersistenceContext annotation to declare JPA provider properties that are passed to the underlying container when the EntityManager instance is created.

66. @PersistenceUnit
The @PersistenceUnit annotation is used to specify the EntityManagerFactory that needs to be injected as a dependency.

67. @PersistenceUnits
The @PersistenceUnits annotation is used to group multiple @PersistenceUnit annotations.

68. @PostLoad
The @PostLoad annotation is used to specify a callback method that fires after an entity is loaded.

69. @PostPersist
The @PostPersist annotation is used to specify a callback method that fires after an entity is persisted.

70. @PostRemove
The @PostRemove annotation is used to specify a callback method that fires after an entity is removed.

71. @PostUpdate
The @PostUpdate annotation is used to specify a callback method that fires after an entity is updated.

72. @PrePersist
The @PrePersist annotation is used to specify a callback method that fires before an entity is persisted.

73. @PreRemove
The @PreRemove annotation is used to specify a callback method that fires before an entity is removed

74. @PreUpdate
The @PreUpdate annotation is used to specify a callback method that fires before an entity is updated.

75. @PrimaryKeyJoinColumn

76. @PrimaryKeyJoinColumns

77. @QueryHint
The @QueryHint annotation is used to specify a JPA provider hint used by a @NamedQuery or a  @NamedNativeQueryannotation

78. @SecondaryTable
The @SecondaryTable annotation is used to specify a secondary table for the currently annotated entity.


79. @SecondaryTables
Được sử dụng để nhóm nhiều @SecondaryTable

80. @SequenceGenerator
Được sử dụng để tăng tự động giá trị khoá chính.

81. @SqlResultSetMapping

82. @SqlResultSetMappings
Được sử dụng để nhóm nhiều @SqlResultSetMapping  lại với nhau

83. @StoredProcedureParameter
Được sử dụng để chỉ ra tham số của @NamedStoredProcedureQuery

84. @Table
Được sử dụng để chỉ ra việc mapping giữa table trong database và entity

85. @TableGenerator

86. @Temporal

87. @Transient
Được sử dụng khi ta không muốn lưu giá trị này xuống database

88. @UniqueConstraint

89. @Version
Được sử dụng để chỉ ra phiên bản đang sử dụng

https://dzone.com/articles/all-jpa-annotations-mapping-annotations

# **5. Kết luận**

Ngày nay thì mình sử dung Restful webservice nhiều hơn SOAP webservice . Vì ưu điểm của Restful là truyền dữ liệu đi nhanh hơn, ít tốn băng thông.

Các em muốn biết Restful là gì thì đọc bài này nhé
[Restfull là gì](https://levunguyen.com/laptrinhspring/2020/05/10/restful/)
