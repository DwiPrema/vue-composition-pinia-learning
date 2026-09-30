<script setup>

const tasks= [
    {
      name: "Website design",
      description: "Define the style guide, branding and create the webdesign on Figma.",
      completed: true
    },
    {
      name: "Website development",
      description: "Develop the portfolio website using Vue JS.",
      completed: false
    },
    {
      name: "Hosting and infrastructure",
      description: "Define hosting, domain and infrastructure for the portfolio website.",
      completed: false
    },
    {
      name: "Composition API",
      description: "Learn how to use the composition API and how it compares to the options API.",
      completed: true
    },
    {
      name: "Pinia",
      description: "Learn how to setup a store using Pinia.",
      completed: true
    },
    {
      name: "Groceries",
      description: "Buy rice, apples and potatos.",
      completed: false
    },
    {
      name: "Bank account",
      description: "Open a bank account for my freelance business.",
      completed: false
    }
];

</script>

<template>

  <main class="container">
    <div class="header">
      <div class="header-side">
        <h1>
          Tasks Manager
        </h1>
      </div>
    </div>
    
    <div class="filters">
      <div>
        <p>Filter by state</p>
        <div class="badges">
          <div class="badge">
            To-Do
          </div>
          <div class="badge">
            Done
          </div>
          <span class="clear">
            x clear
          </span>
        </div>
      </div>
    </div>

    <div class="tasks">
      
      <div class="task">
        <h3>
          Website design
        </h3>
        <p>
          Define the style guide, branding and create the webdesign on Figma.
        </p>
        <div class="task-check">
          <input type="checkbox" checked />
          <label>
            Done
          </label>
        </div>
      </div>

      <div class="task">
        <h3>
          Website development
        </h3>
        <p>
          Develop the portfolio website using Vue JS.
        </p>
        <div class="task-check">
          <input type="checkbox"/>
          <label>
            To-Do
          </label>
        </div>
      </div>

    </div>

    <div class="add-task">
      <h3>Add a new task</h3>
      <input type="text" name="title" placeholder="Enter a title..."><br />
      <textarea name="description" rows="4" placeholder="Enter a description..." /><br />
      <button class="btn gray">Add Task</button>

    </div>

  </main>
  
   

</template>


<style lang="scss" scoped>

.header {
  display: flex;
  justify-content: space-between;
  align-items: center;

  .header-side {
    display: flex;
    align-items: center;

    h1 {
      text-transform: capitalize;
      font-size: 42px;
      font-weight: 700;
      line-height: 47px;
      letter-spacing: 0em;
      text-align: left;
    }

    .secondary {
      margin-left: 12px;
    }
  }

}

.filters {
  display: flex;
  flex-direction: column;
  margin: 40px 0;

  p {
    font-size: 16px;
    font-weight: 400;
    line-height: 21px;
    letter-spacing: 0em;
    text-align: left;
  }

  .badges {
    display: flex;
    flex-wrap: wrap;
    gap: 12px;
    margin: 14px 0;
    align-items: center;
  }

  .clear {
    font-size: 14px;
    font-weight: 400;
    line-height: 16px;
    letter-spacing: 0em;
    text-align: left;
    cursor: pointer;
  }

}

.tasks {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 20px;

  @media (max-width: 768px) {
    grid-template-columns: repeat(1, 1fr);
  }
}

.task {
  display: flex;
  flex-direction: column;
  background-color: var(--white-color);
  color: var(--black-color);
  padding: 20px;
  border-radius: 12px;
  position: relative;


  h3 {
    font-size: 20px;
    font-weight: 700;
    line-height: 21px;
    letter-spacing: 0em;
    text-align: left;
  }

  p {
    margin-top: 24px;
    margin-bottom: 12px;
    font-size: 16px;
    font-weight: 400;
    line-height: 16px;
    letter-spacing: 0em;
    text-align: left;
  }


  .task-check {
    display: flex;
    align-items: center;
    justify-content: center;
    position: absolute;
    bottom: 10px;
    right: 10px;

    label {
      font-size: 13px;
      font-weight: 400;
      line-height: 16px;
      letter-spacing: 0em;
      text-align: left;
      margin-left: 5px;
      cursor: pointer;
    }

    input {
      display: flex;
      justify-content: center;
      align-items: center;
      width: 18px;
      height: 18px;
      border-radius: 100%;
      border: 0.77px solid #AEAEB2;
      appearance: none;
      cursor: pointer;


      &:checked {
        background-color: #0A7AFF;
        border-color: #0A7AFF;

        &::before {
          content: '';
          display: block;
          width: 4.5px;
          height: 9px;
          border: solid white;
          border-width: 0 2px 2px 0;
          transform: rotate(45deg);
        }
      }
    }
  }
}

.add-task {
  margin-top: 60px;

  input, textarea {
    width: 360px;
    max-width: 100%;
    margin-top: 12px;
    padding: 5px;
  }

  button {
    width: 360px;
    margin-top: 12px;
  }
}


</style>