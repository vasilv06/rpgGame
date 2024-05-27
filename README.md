 class Character {
    protected String name;
    protected int health;
    protected int mana;
    protected int level;

    public Character(String name, int health, int mana, int level) {
        this.name = name;
        this.health = health;
        this.mana = mana;
        this.level = level;
    }

    public void attack(Character target) {
        System.out.println(this.name + " attacks " + target.name + "!");
    }

    public void defend() {
        System.out.println(this.name + " defends!");
    }

    public void castSpell(Character target) {
        System.out.println(this.name + " casts a spell on " + target.name + "!");
    }

    public void levelUp() {
        this.level++;
        System.out.println(this.name + " leveled up to " + this.level + "!");
    }
}


class Warrior extends Character {
    private int strength;
    private int armor;

    public Warrior(String name, int health, int mana, int level, int strength, int armor) {
        super(name, health, mana, level);
        this.strength = strength;
        this.armor = armor;
    }

    public void specialAttack(Character target) {
        System.out.println(this.name + " performs a special attack on " + target.name + "!");
    }
}


class Mage extends Character {
    private int intelligence;
    private int spellPower;

    public Mage(String name, int health, int mana, int level, int intelligence, int spellPower) {
        super(name, health, mana, level);
        this.intelligence = intelligence;
        this.spellPower = spellPower;
    }

    public void castFireball(Character target) {
        System.out.println(this.name + " casts Fireball on " + target.name + "!");
    }
}


class Rogue extends Character {
    private int agility;
    private int dexterity;

    public Rogue(String name, int health, int mana, int level, int agility, int dexterity) {
        super(name, health, mana, level);
        this.agility = agility;
        this.dexterity = dexterity;
    }

    public void backstab(Character target) {
        System.out.println(this.name + " performs a backstab on " + target.name + "!");
    }
}


public class Main {
    public static void main(String[] args) {
        Warrior warrior = new Warrior("Aragorn", 100, 30, 1, 20, 10);
        Mage mage = new Mage("Gandalf", 60, 100, 1, 25, 40);
        Rogue rogue = new Rogue("Legolas", 80, 50, 1, 30, 25);

        warrior.attack(mage);
        mage.castFireball(warrior);
        rogue.backstab(warrior);

        warrior.levelUp();
        mage.levelUp();
        rogue.levelUp();
    }
}
