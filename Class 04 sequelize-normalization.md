
# ***Read: Class 04 - sequelize-normalization***

***

## **Associations:**

***

Sequelize supports the standard associations:

- One-To-One.
- One-To-Many.
- Many-To-Many.

To do this, Sequelize provides four types of associations that should be combined to create them:

- The HasOne association.
- The BelongsTo association.
- The HasMany association.
- The BelongsToMany association.

        const A = sequelize.define('A', /* ... */);
        const B = sequelize.define('B', /* ... */);

    A.hasOne(B); -->  A HasOne B

    A.belongsTo(B); --> A BelongsTo B

    A.hasMany(B); --> A HasMany B

    A.belongsToMany(B, { through: 'C' }); --> A BelongsToMany B through the junction table C


- **The A.hasOne(B) association means:** that a One-To-One relationship exists between A and B, with the foreign key being defined in the target model (B).

- **The A.belongsTo(B) association means:** that a One-To-One relationship exists between A and B, with the foreign key being defined in the source model (A).

- **The A.hasMany(B) association means:** that a One-To-Many relationship exists between A and B, with the foreign key being defined in the target model (B).

- **The A.belongsToMany(B, { through: 'C' }) association means:** that a Many-To-Many relationship exists between A and B, using table C as junction table, which will have the foreign keys (aId and bId, for example). Sequelize will automatically create this model C (unless it already exists) and define the appropriate foreign keys on it.

***

## **Creating the standard relationships:**

- To create a One-To-One relationship, the hasOne and belongsTo associations are used together.

- To create a One-To-Many relationship, the hasMany and belongsTo associations are used together.

- To create a Many-To-Many relationship, two belongsToMany calls are used together.

### **One-To-One relationships:**

The main setup to achieve a One-To-One relationship between them such that Bar gets a fooId column is as follows:

        Foo.hasOne(Bar);
        Bar.belongsTo(Foo);

### **One-To-Many relationships:**

The main setup to achieve a One-To-Many relationship between them, meaning that one Team has many Players, while each Player belongs to a single Team, is as follows:

        Team.hasMany(Player);
        Player.belongsTo(Team);

### **Many-To-Many relationships:**

The main setup to achieve a the junction table that will keep track of the associations will be called ActorMovies, which will contain the foreign keys movieId and actorId.

        const Movie = sequelize.define('Movie', { name: DataTypes.STRING });
        const Actor = sequelize.define('Actor', { name: DataTypes.STRING });
        Movie.belongsToMany(Actor, { through: 'ActorMovies' });
        Actor.belongsToMany(Movie, { through: 'ActorMovies' });

***

[README](README.md)
